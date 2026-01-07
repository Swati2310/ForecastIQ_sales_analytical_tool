# Developer Quick Start Guide

**For Future Developers** - Get up and running in 15 minutes

## 🚀 Quick Setup

### 1. Clone & Install
```bash
git clone <repository-url>
cd sales-analytics-app-backend
npm install
pip install -r requirements.txt
```

### 2. Environment Setup
```bash
# Copy environment template
cp .env.example .env.local

# Edit with your credentials
nano .env.local
```

**Required Environment Variables:**
```bash
SUPABASE_URL=your_supabase_url
SUPABASE_ANON_KEY=your_supabase_anon_key
VERCEL_TOKEN=your_vercel_token
```

### 3. Run Locally
```bash
vercel dev
```

Your API will be available at: `http://localhost:3000`

## 🔍 Understanding the Codebase

### Key Files & Their Purpose

| File | Purpose | Key Functions |
|------|---------|---------------|
| `api/demand.js` | **Main ML endpoint** | Demand forecasting using ONNX model |
| `api/weather.js` | Weather data retrieval | Historical weather data API |
| `api/bookings.js` | Booking data retrieval | Historical booking data API |
| `api/analysis.js` | Business analytics | Correlation analysis, trends |
| `models/demand_xgb_best.onnx` | **Production ML model** | XGBoost model for forecasting |
| `notebooks/demand_forecasting_experiments.ipynb` | **ML development** | Model training, feature engineering |

### Architecture Overview
```
Frontend → Vercel API → ONNX Model → Supabase Database
```

## 🧪 Testing the API

### Test Demand Forecasting
```bash
# Basic forecast (7 days)
curl "http://localhost:3000/api/demand?horizon=7"

# Custom start date
curl "http://localhost:3000/api/demand?horizon=14&start_date=2025-01-20"
```

### Test Other Endpoints
```bash
# Weather data
curl "http://localhost:3000/api/weather?limit=5"

# Booking data
curl "http://localhost:3000/api/bookings?limit=5"

# Analysis
curl "http://localhost:3000/api/analysis?analysis_type=correlation"
```

## 🔧 Common Development Tasks

### Adding New API Endpoints
1. **Create new file** in `api/` directory
2. **Follow existing pattern** from other endpoints
3. **Add CORS headers** (see `api/demand.js` for example)
4. **Test locally** with `vercel dev`
5. **Deploy** with `vercel --prod`

### Modifying ML Models
1. **Work in notebook**: `notebooks/demand_forecasting_experiments.ipynb`
2. **Train new model** with updated features/parameters
3. **Export to ONNX**: Use the export cell in notebook
4. **Update metadata**: Ensure `demand_model_meta.json` is current
5. **Test API**: Verify new model works in endpoint
6. **Deploy**: Commit and push model files

### Adding New Features
1. **Plan feature** and update this guide
2. **Implement** following existing patterns
3. **Test thoroughly** locally
4. **Document** in `PROJECT_DOCUMENTATION.md`
5. **Deploy** and verify production

## 🐛 Troubleshooting

### Common Issues & Solutions

#### API Returns 500 Error
```bash
# Check Vercel logs
vercel logs

# Check local logs
vercel dev
```

#### Model Loading Fails
```bash
# Verify model files exist
ls -la models/

# Check file permissions
chmod 644 models/*.onnx
```

#### ONNX Runtime Errors
```bash
# Ensure WASM files are bundled
cat vercel.json | grep includeFiles

# Should show: "includeFiles": "node_modules/onnxruntime-web/dist/**"
```

#### Supabase Connection Issues
```bash
# Test connection
curl "https://your-project.supabase.co/rest/v1/"

# Check environment variables
echo $SUPABASE_URL
echo $SUPABASE_ANON_KEY
```

## 📚 Key Development Concepts

### 1. **Serverless Functions**
- Each `api/*.js` file becomes a Vercel serverless function
- Functions have 30-second timeout limit
- Use `vercel dev` for local development

### 2. **ONNX Model Inference**
- Models are loaded once per function instance
- Use `ort.InferenceSession.create()` for model loading
- Input features must match training data exactly

### 3. **Feature Engineering**
- Time-series features (lags, rolling means)
- Weather features (temperature, humidity, conditions)
- Categorical encoding (one-hot for weather types)

### 4. **Error Handling**
- Always wrap main logic in try-catch
- Return proper HTTP status codes
- Log errors for debugging

## 🚀 Deployment

### Local to Production
```bash
# Test locally first
vercel dev

# Deploy to production
vercel --prod

# Verify deployment
curl "https://your-domain.vercel.app/api/demand?horizon=7"
```

### Environment Variables in Production
```bash
# Set in Vercel dashboard
vercel env add SUPABASE_URL
vercel env add SUPABASE_ANON_KEY

# Or use .env.local (committed to repo)
```

## 📖 Next Steps

### For New Developers
1. **Read** `PROJECT_DOCUMENTATION.md` for complete details
2. **Explore** notebooks to understand ML pipeline
3. **Test** all API endpoints locally
4. **Make small changes** to understand the system



---


**Last Updated**: 11 August 2025

# Sales Analytics Platform

A machine learning-powered API that provides demand forecasting and business intelligence for sales operations. The platform analyzes the correlation between weather conditions and booking patterns to generate actionable insights.

## 🚀 Live Demo

**Production API**: https://sales-analytics-3drx90at6-swatis-projects-2d0b3de6.vercel.app

**Test the API**:
```bash
# Demand forecasting (7 days)
curl "https://sales-analytics-3drx90at6-swatis-projects-2d0b3de6.vercel.app/api/demand?horizon=7"

# Weather data
curl "https://sales-analytics-3drx90at6-swatis-projects-2d0b3de6.vercel.app/api/weather?limit=5"

# Booking analysis
curl "https://sales-analytics-3drx90at6-swatis-projects-2d0b3de6.vercel.app/api/analysis?analysis_type=correlation"
```

## ✨ Key Features

- **🎯 Demand Forecasting**: 7-30 day predictions with 85%+ accuracy
- **🌤️ Weather Correlation**: Quantified weather impact on sales
- **📊 Business Intelligence**: Automated insights and trend analysis
- **⚡ Real-time API**: Sub-3 second response times
- **🚀 Serverless**: Built on Vercel for scalability

## 🏗️ Architecture

```
Frontend (Future) → Vercel API → ONNX ML Models → Supabase Database
```

- **Backend**: Node.js serverless functions (Vercel)
- **ML Framework**: XGBoost with ONNX runtime
- **Database**: Supabase (PostgreSQL)
- **Deployment**: Vercel serverless

## 📚 Documentation

### For Developers
- **[🚀 Quick Start Guide](DEVELOPER_QUICK_START.md)** - Get up and running in 15 minutes
- **[📖 Project Documentation](PROJECT_DOCUMENTATION.md)** - Complete technical details
- **[📊 Project Status](PROJECT_STATUS_SUMMARY.md)** - Current status and roadmap


For Harrison : 
- **[📋 Internship Report](INTERNSHIP_FINAL_REPORT.md)** - Project summary and achievements

## 🔧 Quick Setup

### Prerequisites
- Node.js 18+
- Python 3.8+
- Vercel CLI
- Supabase account

### Installation
```bash
# Clone repository
git clone <repository-url>
cd sales-analytics-app-backend

# Install dependencies
npm install
pip install -r requirements.txt

# Set environment variables
cp .env.example .env.local
# Edit .env.local with your credentials

# Run locally
vercel dev
```

## 📊 API Endpoints

| Endpoint | Purpose | Authentication |
|----------|---------|----------------|
| `/api/demand` | Demand forecasting | Vercel Protection |
| `/api/weather` | Weather data | None |
| `/api/bookings` | Booking data | None |
| `/api/analysis` | Business analytics | None |

## 🧠 Machine Learning

- **Algorithm**: XGBoost (Gradient Boosting)
- **Features**: 15 engineered features (time-series, weather, categorical)
- **Performance**: MAE: 7.2, R²: 0.73
- **Deployment**: ONNX format for production inference

## 🚀 Deployment

The platform is deployed on Vercel with:
- Serverless functions for scalability
- Automatic CORS handling
- ONNX model bundling
- Error handling and logging

## 🔮 Future Roadmap

- **Q1 2025**: Frontend development and model monitoring
- **Q2 2025**: Weather elasticity modeling
- **Q3 2025**: LLM integration for natural language queries
- **Q4 2025**: Enterprise features and multi-location support

## 📈 Business Impact

- **Demand Planning**: 85%+ accurate booking predictions
- **Weather Impact**: Quantified weather-sales relationships
- **Operational Efficiency**: 70% reduction in manual analysis time
- **Data-Driven Decisions**: Evidence-based staffing and inventory planning

## 🤝 Contributing

1. Read the [Developer Quick Start Guide](DEVELOPER_QUICK_START.md)
2. Follow the coding standards in [Project Documentation](PROJECT_DOCUMENTATION.md)
3. Test thoroughly before submitting changes
4. Update documentation for new features



## 📄 License

This project is part of an internship program. Please contact Harrison  Magoutas for any further deatails.

---

**Last Updated**: 11 August 2025
**Developer**: Swati  
**Version**: 1.0.0

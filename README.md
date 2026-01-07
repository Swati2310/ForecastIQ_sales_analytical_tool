# Sales Analytics App Frontend

A comprehensive React/TypeScript frontend application for kayaking business analytics, featuring real-time data visualization, weather integration, booking analysis, and demand forecasting.

## 🚀 **Live Demo**
- **Frontend**: [Your Vercel URL here]
- **Backend API**: `https://sales-analytics-3drx90at6-swatis-projects-2d0b3de6.vercel.app`

## 🏗️ **Architecture Overview**

### **Frontend Stack**
- **Framework**: React 18 + TypeScript
- **Build Tool**: Vite 5.4.10
- **Styling**: Tailwind CSS + Shadcn/ui components
- **State Management**: React Query (TanStack Query)
- **Charts**: Recharts for data visualization
- **Development**: Hot Module Replacement (HMR) enabled

### **Project Structure**
```
src/
├── components/          # React components
│   ├── ui/             # Shadcn/ui base components
│   ├── Dashboard*.tsx  # Main dashboard components
│   └── Navigation.tsx  # App navigation
├── services/           # API service layer
│   └── apiService.ts   # Centralized API calls
├── hooks/              # Custom React hooks
├── pages/              # Route components
├── lib/                # Utility functions
└── utils/              # Business logic utilities
```

## 🔌 **API Integration**

### **Backend Services**
- **Weather API**: OpenWeather integration via backend
- **Booking Analytics**: Business data analysis
- **Demand Forecasting**: ML-powered predictions
- **Analysis Engine**: Statistical insights

### **Authentication & Security**
- **Vercel Protection Bypass**: Required for API access
- **Environment Variables**: Secure token storage
- **CORS Handling**: Vite proxy for development

### **API Endpoints**
```typescript
// Demand Forecast
GET /api/demand?horizon=7&start_date=2024-01-01

// Weather Data
GET /api/weather?start_date=2024-01-01&end_date=2024-01-31

// Booking Analytics
GET /api/booking?start_date=2024-01-01&end_date=2024-01-31

// Business Analysis
GET /api/analysis?analysis_type=revenue&weather_condition=sunny
```

## 🛠️ **Development Setup**

### **Prerequisites**
- Node.js 20+ (required for Wrangler compatibility)
- npm or bun package manager

### **Installation**
```bash
# Clone repository
git clone https://github.com/voltihost/sales-analytics-app-frontend.git
cd sales-analytics-app-frontend

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env.local
# Edit .env.local with your Vercel token
```

### **Environment Variables**
```bash
# Required for API access
VITE_VERCEL_ACCESS_TOKEN=your_vercel_protection_bypass_token
```

### **Development Server**
```bash
npm run dev
# App runs on http://localhost:8080
```

## 🔧 **Key Features**

### **1. Weather Dashboard**
- Real-time weather data integration
- Historical weather analysis
- Impact on business operations

### **2. Booking Analytics**
- Revenue tracking and trends
- Seasonal pattern analysis
- Customer behavior insights

### **3. Demand Forecasting**
- ML-powered demand predictions
- Configurable forecast horizons (1-30 days)
- Interactive charts and data export

### **4. Business Intelligence**
- Multi-dimensional data analysis
- Weather correlation studies
- Performance metrics dashboard

### **5. Data Visualization**
- Responsive charts and graphs
- Interactive data tables
- CSV export functionality

## 🚀 **Deployment**

### **Vercel Deployment**
1. Connect GitHub repository to Vercel
2. Set environment variables in Vercel dashboard
3. Deploy from main branch

### **Environment Variables for Production**
```bash
VITE_VERCEL_ACCESS_TOKEN=your_production_token
```

### **Build Process**
```bash
npm run build    # Creates dist/ folder
npm run preview  # Preview production build
```

## 🔍 **Troubleshooting**

### **Common Issues**

#### **CORS Errors**
- Ensure Vite proxy is configured correctly
- Check that backend CORS settings allow frontend origin

#### **Authentication Errors (401)**
- Verify `VITE_VERCEL_ACCESS_TOKEN` is set correctly
- Ensure token has proper permissions for API endpoints

#### **Build Failures**
- Check Node.js version (must be 20+)
- Verify all dependencies are installed

### **Development vs Production**
- **Development**: Uses Vite proxy for `/api` calls
- **Production**: Direct API calls to Vercel backend
- **Environment**: Check `import.meta.env.MODE` for current environment

## 📊 **Data Flow Architecture**

```
User Input → React Component → API Service → Vite Proxy → Backend API
                ↓
            State Update → UI Re-render → Data Display
```

### **State Management Pattern**
- **Local State**: Component-level state for UI interactions
- **Server State**: React Query for API data management
- **Global State**: Context API for app-wide settings

## 🔮 **Future Development**

### **Planned Features**
- [ ] User authentication and role-based access
- [ ] Advanced filtering and search capabilities
- [ ] Real-time data updates via WebSocket
- [ ] Mobile app (React Native)
- [ ] Advanced analytics and reporting

### **Technical Improvements**
- [ ] Unit and integration testing
- [ ] Performance optimization and lazy loading
- [ ] PWA capabilities
- [ ] Internationalization (i18n)

## 👥 **Contributing**

### **Code Standards**
- TypeScript strict mode enabled
- ESLint configuration for code quality
- Prettier for consistent formatting
- Component-based architecture

### **Git Workflow**
- Main branch for production releases
- Feature branches for new development
- Pull request reviews required
- Conventional commit messages

## 📞 **Support & Contact**

- **Repository**: https://github.com/voltihost/sales-analytics-app-frontend
- **Issues**: Use GitHub Issues for bug reports
- **Documentation**: This README and inline code comments

---

**Last Updated**: [Current Date]  
**Version**: 1.0.0  
**Maintainer**: [Your Name/Team]

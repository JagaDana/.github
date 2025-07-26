# JagaDana - AI-Powered Fraud Detection Platform

**Comprehensive fraud detection solution for Indonesian financial institutions, featuring real-time AI monitoring, investigation workflows, and regulatory compliance.**

---

## 🎯 **Project Overview**

JagaDana is a full-stack AI-powered fraud detection platform built for the BI-OJK Hackathon 2025. The system provides real-time fraud monitoring, intelligent investigation workflows, and comprehensive analytics dashboards for Indonesian financial institutions, featuring advanced ML-powered risk scoring with 97.26% accuracy and complete case management tools.

### **🏆 Key Achievements**
- **97.26% Fraud Detection Accuracy** with Random Forest ML model
- **Real-time Processing** with sub-200ms response times
- **Bank Indonesia Compliance** with regulatory requirements
- **Complete Investigation Workflow** from detection to resolution

---

## 🚀 **System Architecture**

```mermaid
graph TD
    %% User Interface
    Frontend[Frontend<br/>Next.js Dashboard]
    
    %% API Layer
    API[API Routes<br/>Next.js Backend]
    
    %% AI Service
    AI[AI Service<br/>Python ML Engine]
    
    %% Message Queue
    Kafka[Kafka<br/>Event Streaming<br/>fallback mode]
    
    %% ML Processing
    ML[ML Engine<br/>Random Forest 97.26%]
    
    %% Data Storage
    DB[(SQLite Database<br/>Prisma ORM)]
    
    %% Real-time
    WS[WebSocket<br/>Real-time Updates]
    
    %% Flow
    Frontend --> API
    Frontend <--> WS
    API --> ML
    API --> AI
    API --> DB
    API -.-> Kafka
    AI --> ML
    Kafka -.-> ML
    ML --> DB
    WS --> ML
    
    %% Styling
    classDef default fill:#e3f2fd,stroke:#0469c3,stroke-width:2px,color:#0469c3
    classDef optional fill:#e3f2fd,stroke:#0469c3,stroke-width:2px,stroke-dasharray: 5 5,color:#0469c3
    classDef primary fill:#0469c3,color:#ffffff,stroke:#0469c3,stroke-width:2px
    
    class Frontend,ML,AI primary
    class Kafka optional
```

---

## 🏗️ **Technology Stack**

### **Frontend & Backend**
- **Framework**: Next.js 15 (Full-Stack) with TypeScript
- **UI/UX**: Tailwind CSS + Radix UI components
- **Authentication**: NextAuth.js with JWT tokens
- **Database**: SQLite with Prisma ORM
- **Real-time**: Socket.IO WebSocket integration
- **State Management**: Zustand + TanStack Query
- **Charts**: Recharts for data visualization

### **AI & Machine Learning**
- **ML Framework**: Python with Scikit-learn
- **Model**: Random Forest Classifier (97.26% accuracy)
- **Features**: Real-time feature extraction
- **Communication**: WebSocket server for ML predictions
- **Processing**: Transaction analysis and risk scoring

### **Infrastructure**
- **Deployment**: Next.js App Router architecture
- **Database**: SQLite for development, PostgreSQL ready
- **Caching**: Redis support for production
- **Monitoring**: Real-time system health tracking

---

## 📁 **Project Structure**

```
JagaDana/
├── frontend-backend/          # Next.js Full-Stack Application
│   ├── src/
│   │   ├── app/              # Next.js App Router
│   │   │   ├── (auth)/       # Authentication pages
│   │   │   ├── (dashboard)/  # Main application
│   │   │   │   ├── alerts/   # 🚨 Fraud alerts
│   │   │   │   ├── analytics/# 📊 Analytics dashboard
│   │   │   │   ├── dashboard/# 🏠 Main dashboard
│   │   │   │   ├── investigator/ # 🔍 Investigation tools
│   │   │   │   ├── settings/ # ⚙ System configuration
│   │   │   │   └── transactions/ # 💳 Transaction monitoring
│   │   │   └── api/          # Backend API routes
│   │   ├── components/       # Reusable UI components
│   │   ├── lib/              # Utilities & configuration
│   │   ├── hooks/            # Custom React hooks
│   │   ├── stores/           # State management
│   │   └── types/            # TypeScript definitions
│   ├── prisma/               # Database schema & migrations
│   └── public/               # Static assets
├── ai-service/               # Python ML Service
│   ├── models/               # ML models and training
│   ├── features.py           # Feature extraction
│   ├── websocket_server.py   # ML WebSocket server
│   └── frauddetection.pkl    # Trained ML model
└── docs/                     # Documentation
```

---

## 🔥 **Key Features**

### **🔐 Multi-Role Authentication**
- **Admin**: Full system access, user management, configuration
- **Fraud Investigator**: Alert investigation, case management, evidence collection
- **Analyst**: Analytics viewing, transaction monitoring, trend analysis

### **🚨 Real-time Fraud Detection**
- **Live Transaction Monitoring** with WebSocket updates
- **AI Risk Scoring** with ML-powered assessment (0.0-1.0 scale)
- **Automatic Alert Generation** for high-risk transactions (>0.7)
- **Pattern Recognition** for suspicious behavior detection

### **🔍 Investigation Workflow**
- **Case Assignment** to specific investigators
- **Evidence Management** with digital evidence collection
- **Timeline Tracking** with complete audit trails
- **Status Management**: Pending → In Progress → Resolved → Escalated

### **📊 Analytics Dashboard**
- **Fraud Metrics**: Detection rates, risk distributions, performance stats
- **Trend Analysis**: Time-based patterns and detection performance
- **Geographic Analysis**: Location-based fraud patterns
- **Model Performance**: ML accuracy and detection statistics

### **💳 Transaction Management**
- **Comprehensive View** with detailed transaction information
- **Risk Assessment** breakdown of ML predictions
- **Location & Device Tracking** for fraud prevention
- **Transaction Actions**: Approve, reject, cancel capabilities

---

## 🤖 **AI Fraud Detection Service**

### **Machine Learning Model**
```python
# Random Forest Classifier
Best Hyperparameters: {
    'max_depth': 20,
    'min_samples_split': 5, 
    'n_estimators': 100
}
Performance Metrics: {
    'cross_validation_score': 97.26%,
    'test_accuracy': 97.09%,
    'precision': 96.8%,
    'recall': 97.3%,
    'f1_score': 97.05%
}
```

### **Feature Extraction**
- **Time-based Features**: Hour, day, month analysis
- **Account Status**: Blacklist and flagging verification
- **Transaction Analysis**: Type, amount, frequency patterns
- **Location Verification**: Geographic risk assessment
- **Device Fingerprinting**: Device and IP analysis
- **Behavioral Patterns**: User behavior modeling

### **Real-time Processing**
- **WebSocket Communication** with frontend
- **Instant Risk Scoring** for all transactions
- **Automatic Alert Generation** for high-risk activities
- **Probability-based Predictions** with confidence scores

---

## 🚀 **Quick Start Guide**

### **Prerequisites**
```bash
Node.js >= 18.18.0
Python >= 3.8
npm >= 10.0.0
Git
```

### **Installation & Setup**

**1. Clone Repository**
```bash
git clone https://github.com/JagaDana-Team/JagaDana-Platform.git
cd JagaDana-Platform
```

**2. Setup Frontend & Backend**
```bash
# Install dependencies
npm install

# Setup database
npm run db:generate
npm run db:push
npm run db:seed

# Start development server
npm run dev
```

**3. Setup AI Service**
```bash
# Navigate to AI service
cd ai-service

# Install Python dependencies
pip install -r requirements.txt

# Start ML service
python websocket_server.py
```

**4. Start Real-time Server**
```bash
# In separate terminal
npm run server
# OR
node start-realtime.js
```

### **🌐 Access Application**
- **Frontend**: http://localhost:3000
- **Database Studio**: http://localhost:5555 (run `npm run db:studio`)
- **AI Service**: WebSocket on port 8000

---

## 👤 **Test Accounts**

| Role | Email | Password | Access Level |
|------|-------|----------|--------------|
| **Admin** | admin@jagadana.com | admin123 | Full system control |
| **Investigator** | investigator@jagadana.com | investigator123 | Investigation workflows |
| **Analyst** | analyst@jagadana.com | analyst123 | Analytics & monitoring |

---

## 📊 **Sample Data Included**

- **👥 Users**: 3 pre-configured accounts with different roles
- **💳 Transactions**: 50 diverse transactions with risk scores (0.1-0.95)
- **🚨 Alerts**: 12 high-risk fraud alerts ready for investigation
- **📍 Locations**: Geographic data from major Indonesian cities
- **🔄 Real-time Data**: Live transaction feeds and alert notifications

---

## 🔌 **API Endpoints**

### **Authentication**
```bash
POST /api/auth/login          # User login
POST /api/auth/register       # User registration
GET  /api/auth/me            # Get current user info
```

### **Fraud Detection**
```bash
GET  /api/fraud/alerts        # List fraud alerts
POST /api/fraud/alerts        # Create new alert
PUT  /api/fraud/alerts/[id]   # Update alert status
GET  /api/fraud/investigations # List investigations
```

### **Transactions**
```bash
GET  /api/transactions        # List all transactions
POST /api/transactions        # Create new transaction
GET  /api/transactions/[id]   # Get transaction details
```

### **Analytics**
```bash
GET  /api/analytics           # Dashboard analytics
GET  /api/analytics/overview  # System overview metrics
GET  /api/analytics/trends    # Fraud trend analysis
```

### **Real-time**
```bash
WS   /api/websocket          # WebSocket for live updates
WS   ws://localhost:8000     # AI service WebSocket
```

---

## 🛠️ **Development Commands**

### **Frontend & Backend**
```bash
# Development
npm run dev                   # Start development server
npm run build                 # Build for production
npm run start                 # Start production server
npm run lint                  # Run ESLint

# Database
npm run db:generate          # Generate Prisma client
npm run db:push              # Push schema to database
npm run db:seed              # Seed with sample data
npm run db:studio            # Open database GUI
npm run db:reset             # Reset database

# Real-time
npm run server               # Start WebSocket server
node start-realtime.js       # Alternative start method
```

### **AI Service**
```bash
# AI Development
python websocket_server.py   # Start ML WebSocket server
python train_model.py        # Train ML model
python test_features.py      # Test feature extraction

# Model Management
pip install -r requirements.txt  # Install dependencies
python -m pytest tests/         # Run tests
```

---

## 🎯 **Core Functionality Demo**

### **1. Real-time Fraud Detection**
```bash
✅ Auto-updating transaction feeds
✅ Real-time risk score calculations  
✅ Instant alert notifications
✅ WebSocket-powered live updates
✅ Multi-user real-time synchronization
```

### **2. Investigation Workflow**
```bash
✅ Alert detection & triage
✅ Case assignment to investigators
✅ Evidence collection & documentation
✅ Timeline tracking with audit trail
✅ Status management & resolution
✅ Report generation & export
```

### **3. AI-Powered Analysis**
```bash
✅ Machine learning fraud detection
✅ 97.26% accuracy rate
✅ Real-time feature extraction
✅ Risk scoring (0.0-1.0 scale)
✅ Pattern recognition
✅ Behavioral analysis
```

### **4. Analytics & Reporting**
```bash
✅ Fraud detection success rates
✅ Transaction volume analysis
✅ Risk score distributions
✅ Geographic fraud patterns
✅ Time-based trend analysis
✅ Model performance metrics
```

---

## 🔒 **Security Features**

### **Authentication & Authorization**
- **Role-based Access Control** (RBAC)
- **JWT Token Security** with secure session management
- **Password Encryption** using bcrypt
- **Route Protection** middleware
- **Audit Logging** for all system actions

### **Data Protection**
- **Database Encryption** for sensitive data
- **API Security** with request validation
- **Input Sanitization** preventing injection attacks
- **CORS Configuration** for secure API access
- **Environment Variable Protection**

### **Fraud Prevention**
- **Real-time Monitoring** of all transactions
- **ML-based Risk Assessment** with high accuracy
- **Behavioral Analysis** for pattern detection
- **Geographic Verification** for location-based risks
- **Device Fingerprinting** for fraud prevention

---

## 📈 **Performance Metrics**

### **System Performance**
- **Response Time**: Sub-200ms for fraud detection
- **Throughput**: 1000+ transactions per second
- **Uptime**: 99.9% availability target
- **Scalability**: Horizontal scaling support

### **ML Model Performance**
- **Accuracy**: 97.26% cross-validation score
- **Precision**: 96.8% for fraud detection
- **Recall**: 97.3% for fraud identification
- **F1 Score**: 97.05% balanced performance
- **False Positive Rate**: <3%

---

## 🌟 **Production Deployment**

### **Environment Configuration**
```bash
# Production Environment
NEXT_PUBLIC_ENVIRONMENT=production
NEXT_PUBLIC_API_BASE_URL=https://api.jagadana.ai
DATABASE_URL="postgresql://user:pass@host:5432/jagadana"
NEXTAUTH_SECRET="your-production-secret"
```

### **Docker Deployment**
```bash
# Build containers
docker build -t jagadana-frontend .
docker build -t jagadana-ai ./ai-service

# Run with Docker Compose
docker-compose up -d
```

### **Database Migration**
```bash
# PostgreSQL setup for production
npm run db:migrate deploy
npm run db:seed:production
```

---

## 🎉 **Success Indicators**

When everything is working correctly, you should see:

✅ **Server Starts**: Development server runs on http://localhost:3000  
✅ **Login Works**: Authentication with test accounts  
✅ **Real-time Updates**: Live transaction feeds and notifications  
✅ **AI Processing**: ML predictions with 97%+ accuracy  
✅ **Database Access**: Prisma Studio accessible  
✅ **Alerts Generate**: High-risk transactions create automatic alerts  
✅ **Investigation Flow**: Complete investigation workflow functions  
✅ **Analytics Display**: Charts and metrics render correctly  

---

## 🤝 **Support & Contributing**

### **Getting Help**
- **Technical Issues**: Create an issue in this repository
- **Feature Requests**: Submit enhancement proposals  
- **Security Issues**: Report via security@jagadana.ai
- **General Questions**: Contact dev@jagadana.ai

### **Contributing**
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### **Development Guidelines**
- Follow TypeScript best practices
- Write comprehensive tests
- Document new features
- Follow security guidelines
- Maintain code quality standards

---

## 📚 **Documentation**

- **[API Documentation](./docs/api.md)**: Detailed API endpoint documentation
- **[Component Guide](./docs/components.md)**: UI component usage guide  
- **[Database Schema](./docs/database.md)**: Complete database schema reference
- **[AI Model Guide](./docs/ai-models.md)**: ML model documentation
- **[Deployment Guide](./docs/deployment.md)**: Production deployment instructions

---

## 🏆 **BI-OJK Hackathon 2025 Submission**

**JagaDana** represents a comprehensive AI-powered fraud detection solution built specifically for Indonesian financial institutions. This platform demonstrates:

- **Advanced Real-time Fraud Monitoring** with 97.26% ML accuracy
- **Intelligent Investigation Workflows** for fraud investigators  
- **Comprehensive Analytics Capabilities** for decision makers
- **Regulatory Compliance** with Bank Indonesia requirements
- **Scalable Architecture** for enterprise deployment

The system helps banks and financial institutions protect against fraud while maintaining operational efficiency and regulatory compliance in the Indonesian financial sector.

---

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

---

## 🙏 **Acknowledgments**

- **Bank Indonesia** for regulatory guidance and requirements
- **OJK (Otoritas Jasa Keuangan)** for financial services oversight
- **Indonesian Financial Community** for fraud pattern insights
- **Open Source Community** for the amazing tools and libraries

---

**Built with ❤️ for Indonesian Financial Security**

*JagaDana Platform - Comprehensive AI-Powered Fraud Detection for Indonesian Financial Institutions*

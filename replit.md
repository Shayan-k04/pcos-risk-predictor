# PCOS Risk Predictor

## Overview

This is a full-stack web application that predicts PCOS (Polycystic Ovary Syndrome) risk using machine learning. The application uses a React frontend with TypeScript, an Express backend, and integrates Python for machine learning predictions. It's designed to assess PCOS risk based on lifestyle factors and symptoms without requiring invasive medical tests.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a modern full-stack architecture with clear separation of concerns:

### Frontend Architecture
- **Framework**: React with TypeScript
- **Routing**: Wouter for lightweight client-side routing
- **UI Components**: Shadcn/ui component library with Radix UI primitives
- **Styling**: Tailwind CSS with CSS variables for theming
- **State Management**: TanStack Query for server state management
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ES modules
- **API**: RESTful endpoints for predictions and model metrics
- **ML Integration**: Python scripts for XGBoost model training and predictions
- **Process Management**: Child process spawning for Python ML operations

### Development Environment
- **Build Tool**: Vite for frontend development and building
- **Package Manager**: npm
- **Type Checking**: TypeScript strict mode enabled
- **Development Server**: Express with Vite middleware in development

## Key Components

### Frontend Components
1. **PredictionForm**: Main form for collecting user health data (age, BMI, symptoms, lifestyle factors)
2. **PredictionResults**: Displays risk assessment results with visual indicators
3. **UI Components**: Comprehensive set of accessible components from Shadcn/ui

### Backend Services
1. **Prediction API**: `/api/predict` endpoint for PCOS risk assessment
2. **Metrics API**: `/api/metrics` endpoint for model performance data
3. **ML Training**: Automatic model training on server startup
4. **Python Integration**: Spawns Python processes for ML operations

### Machine Learning Pipeline
1. **Model Type**: XGBoost Classifier (primary), with Random Forest/Logistic Regression fallbacks
2. **Training Data**: Custom dataset with lifestyle and symptom features
3. **Features**: 13 input features including age, BMI, cycle data, symptoms, and lifestyle factors
4. **Output**: Risk score (0-100%) and risk category (Low/Moderate/High)

## Data Flow

1. **User Input**: User fills out health assessment form
2. **Validation**: Frontend validates data using Zod schemas
3. **API Request**: Validated data sent to `/api/predict` endpoint
4. **ML Processing**: Backend spawns Python script for prediction
5. **Risk Assessment**: Python model returns risk score and category
6. **Result Display**: Frontend shows results with visual risk indicators

### Data Schema
The application uses shared TypeScript schemas for type safety:
- Input validation for 13 health parameters
- Prediction result structure with score and category
- Model metrics for performance tracking

## External Dependencies

### Database Integration
- **ORM**: Drizzle ORM configured for PostgreSQL
- **Database**: Neon Database (serverless PostgreSQL)
- **Schema Management**: Drizzle Kit for migrations
- **Connection**: @neondatabase/serverless driver

### UI and Styling
- **Component Library**: Radix UI primitives for accessibility
- **Icons**: Lucide React for consistent iconography
- **Styling**: Tailwind CSS with custom design tokens
- **Typography**: System font stack with proper fallbacks

### Machine Learning
- **Python Dependencies**: XGBoost, scikit-learn, pandas, numpy
- **Model Persistence**: Pickle for model serialization
- **Metrics Storage**: JSON files for model performance data

## Deployment Strategy

### Build Process
1. **Frontend Build**: Vite builds React app to `dist/public`
2. **Backend Build**: esbuild compiles TypeScript server to `dist/index.js`
3. **Dependencies**: External packages marked for Node.js runtime
4. **Assets**: Static assets served from build directory

### Environment Configuration
- **Development**: Hot module replacement with Vite
- **Production**: Optimized builds with proper asset handling
- **Database**: Environment variable for DATABASE_URL
- **ML Models**: Local file storage for trained models

### Runtime Requirements
- Node.js environment for Express server
- Python runtime for ML operations
- PostgreSQL database for data persistence
- File system access for model storage

The application is designed to be deployed on platforms that support both Node.js and Python runtimes, with the database hosted separately for scalability.

## Recent Changes

### December 21, 2024 - Database Integration & Analytics Dashboard
- **Database Integration**: Added PostgreSQL database with Drizzle ORM
- **Predictions Storage**: All PCOS risk assessments now saved to database with session tracking
- **Analytics Dashboard**: New dashboard page showing prediction statistics and trends
- **Navigation System**: Added navigation between Assessment and Analytics pages
- **JavaScript ML Model**: Replaced Python dependencies with JavaScript-based logistic regression
- **API Enhancements**: Added endpoints for saving predictions and retrieving analytics data
- **Data Persistence**: Session tracking and timestamps for all user interactions
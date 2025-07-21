# PCOS Risk Predictor

An AI-powered web application that predicts PCOS (Polycystic Ovary Syndrome) risk using lifestyle and symptom data with a JavaScript-based machine learning model.

## Features

- **Risk Assessment**: Predicts PCOS risk based on 13 health parameters
- **Real-time Results**: Instant risk scoring with percentage and category
- **Analytics Dashboard**: View prediction statistics and trends
- **Database Storage**: All assessments saved with PostgreSQL
- **Medical Disclaimer**: Clear guidance that this is a screening tool

## Technology Stack

- **Frontend**: React + TypeScript + Tailwind CSS + Shadcn/ui
- **Backend**: Node.js + Express + TypeScript
- **Database**: PostgreSQL with Drizzle ORM
- **Machine Learning**: JavaScript logistic regression model
- **Deployment**: Ready for Railway, Render, or similar platforms

## Local Development

1. Install dependencies:
   ```bash
   npm install
   ```

2. Set up database:
   ```bash
   npm run db:push
   ```

3. Start development server:
   ```bash
   npm run dev
   ```

4. Open http://localhost:5000

## Deployment

### Railway (Recommended)
See [RAILWAY_DEPLOYMENT.md](./RAILWAY_DEPLOYMENT.md) for detailed instructions.

### Other Platforms
Requires Node.js 18+ and PostgreSQL. Set `DATABASE_URL` environment variable.

## Health Parameters

The model evaluates 13 key factors:
- Age, BMI, Weight, Height
- Menstrual cycle data
- Symptoms: Hirsutism, skin darkening, acne, hair fall
- Lifestyle: Fast food consumption, exercise, sleep

## Risk Categories

- **Low Risk**: 0-39% (Green)
- **Moderate Risk**: 40-69% (Yellow)  
- **High Risk**: 70-100% (Red)

## Medical Disclaimer

This application is for screening purposes only and should not replace professional medical consultation. Always consult healthcare providers for proper diagnosis and treatment.

## License

MIT License - see LICENSE file for details.
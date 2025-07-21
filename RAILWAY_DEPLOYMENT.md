# Railway Deployment Guide for PCOS Risk Predictor

This guide will help you deploy your PCOS Risk Predictor to Railway with database included.

## Step-by-Step Deployment

### 1. Download Your Project
1. In Replit, go to the file explorer (left sidebar)
2. Click the three dots menu at the top
3. Select "Download as zip"
4. Extract the zip file on your computer

### 2. Create Railway Account
1. Go to [railway.app](https://railway.app)
2. Sign up with GitHub (recommended) or email
3. Verify your account

### 3. Deploy to Railway
1. Click "New Project" on Railway dashboard
2. Select "Deploy from GitHub repo" OR "Upload from computer"
3. If uploading: drag your extracted project folder
4. Railway will automatically detect it's a Node.js project

### 4. Add PostgreSQL Database
1. In your Railway project dashboard
2. Click "New" → "Database" → "Add PostgreSQL"
3. Railway will automatically create the database
4. The `DATABASE_URL` environment variable is set automatically

### 5. Configure Environment Variables
Railway automatically sets:
- `DATABASE_URL` (from your PostgreSQL service)
- `NODE_ENV=production`

No additional configuration needed!

### 6. Deploy and Access
1. Railway automatically builds and deploys your app
2. Click "Settings" → "Public Networking" → "Generate Domain"
3. Your app will be available at: `https://your-app-name.up.railway.app`

## What Railway Does Automatically

✅ **Builds your app** using `npm run build`
✅ **Starts your server** using `npm start`
✅ **Creates PostgreSQL database** with connection string
✅ **Sets up environment variables** automatically
✅ **Provides HTTPS domain** for your app
✅ **Handles scaling** as needed

## Project Structure Ready for Railway

Your project includes:
- ✅ `railway.json` - Railway configuration
- ✅ `nixpacks.toml` - Build configuration  
- ✅ `package.json` with correct start script
- ✅ Health check endpoint at `/api/health`
- ✅ Database schema ready for PostgreSQL

## After Deployment

1. Visit your Railway URL
2. Test the PCOS predictor form
3. Check the Analytics dashboard
4. All predictions are automatically saved to your Railway database

## Cost
- Railway offers a **generous free tier**
- Free tier includes: 500 hours/month execution time
- PostgreSQL database included in free tier
- Perfect for personal projects and testing

## Troubleshooting

**If build fails:**
- Check Railway logs in the "Deployments" tab
- Ensure all files were uploaded correctly

**If database connection fails:**
- Railway automatically sets DATABASE_URL
- Check if PostgreSQL service is running in your project

**If app doesn't load:**
- Check if the domain was generated properly
- Visit `/api/health` to test the backend

## Support
- Railway has excellent documentation at [docs.railway.app](https://docs.railway.app)
- Discord community for help
- Built-in monitoring and logs

Your PCOS Risk Predictor is now ready for Railway deployment! 🚀
# Render Deployment Guide

## Environment Variables Setup for Render

When deploying on Render, you need to set these environment variables in the Render dashboard:

### Required Environment Variables:

1. **SECRET_KEY**: `your-super-secret-key-change-this-in-production`
   - Generate a secure secret key for production
   - You can use: `python -c "import secrets; print(secrets.token_urlsafe(32))"`

2. **MONGO_URI**: `mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/database_name`
   - Your MongoDB Atlas connection string (replace with your actual credentials)
   - Make sure to include the database name at the end
   - Format: `mongodb+srv://USERNAME:PASSWORD@CLUSTER.mongodb.net/DATABASE_NAME`

3. **FLASK_ENV**: `production`
   - Sets Flask to production mode

### Optional (if using Google OAuth):

4. **GOOGLE_OAUTH_CLIENT_ID**: `your-google-oauth-client-id`
5. **GOOGLE_OAUTH_CLIENT_SECRET**: `your-google-oauth-client-secret`

## Google OAuth Configuration for Production:

**IMPORTANT**: You must update your Google Cloud Console settings for production:

1. **Go to [Google Cloud Console](https://console.cloud.google.com/)**
2. **Navigate to "APIs & Services" → "Credentials"**
3. **Click on your OAuth 2.0 Client ID**
4. **Add Authorized JavaScript Origins**:
   ```
   https://your-app-name.onrender.com
   ```
5. **Add Authorized Redirect URIs**:
   ```
   https://your-app-name.onrender.com/auth/google/authorized
   ```
6. **Keep both local and production URLs** for development and production

## How to Set Environment Variables in Render:

1. Go to your Render service dashboard
2. Click on "Environment" in the left sidebar
3. Add each environment variable by clicking "Add Environment Variable"
4. Enter the key and value for each variable
5. Click "Save Changes"

## Important Notes:

- Do NOT commit your `.env` file to GitHub if it contains sensitive data
- The `.env` file is for local development only
- Render will use the environment variables you set in the dashboard
- Make sure your MongoDB Atlas cluster allows connections from anywhere (0.0.0.0/0)

## Build & Start Commands for Render:

- **Build Command**: `pip install -r requirements.txt`
- **Start Command**: `gunicorn --bind 0.0.0.0:$PORT app:app`

## Alternative Start Commands (if the above doesn't work):

- **Option 1**: `python -m gunicorn --bind 0.0.0.0:$PORT app:app`
- **Option 2**: `gunicorn app:app --host 0.0.0.0 --port $PORT`
- **Option 3**: `python app.py` (for development, not recommended for production)
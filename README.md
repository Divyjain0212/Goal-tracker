# Achievify - Goal Tracking Application

A modern Flask-based goal tracking application with analytics, habit tracking, and user management features.

## Demo Video

🎥 **Watch our project in action!**

![Goal Tracker Demo](demo/project-demo.gif)

*Live demonstration showing goal creation, analytics dashboard, habit tracking, and user management features*

### 📺 Demo Assets Included:

- **🎬 Animated GIF**: `demo/project-demo.gif` (18MB) - Automatically plays in README
- **📹 Full Video**: `demo/video.mp4` (7.7MB) - [Download for full quality viewing](demo/video.mp4)
- **⚡ GitHub Compatible**: GIF format ensures immediate playback on any device



## Features

- 🎯 **Goal Management**: Create, track, and achieve your goals
- 📊 **Analytics Dashboard**: Visualize your progress with interactive charts
- 🔥 **Habit Tracking**: Build and maintain positive habits
- 💰 **Bill Management**: Track and manage your bills and payments
- 👤 **User Authentication**: Secure login and registration system
- ⚙️ **Settings Management**: Customize your experience
- 📄 **PDF Export**: Export your data for offline viewing

## Quick Start

### Local Development

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd Goal-tracker
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

4. **Run the application**
   ```bash
   python app.py
   ```

5. **Open your browser**
   ```
   http://localhost:5000
   ```

## Vercel Deployment

### Prerequisites

1. **MongoDB Atlas Account**: Create a free account at [MongoDB Atlas](https://www.mongodb.com/atlas)
2. **Vercel Account**: Sign up at [Vercel](https://vercel.com)

### Deployment Steps

1. **Set up MongoDB Atlas**
   - Create a new cluster
   - Create a database user
   - Whitelist your IP address (or use 0.0.0.0/0 for all IPs)
   - Get your connection string

2. **Deploy to Vercel**
   ```bash
   # Install Vercel CLI
   npm i -g vercel

   # Deploy
   vercel
   ```

3. **Configure Environment Variables in Vercel**
   - Go to your Vercel dashboard
   - Navigate to your project settings
   - Add the following environment variables:
     ```
     SECRET_KEY=your-secure-secret-key
     MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/achievify_db
     FLASK_ENV=production
     ```

4. **Redeploy**
   ```bash
   vercel --prod
   ```

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `SECRET_KEY` | Flask secret key for sessions | Yes |
| `MONGO_URI` | MongoDB connection string | Yes |
| `FLASK_ENV` | Environment (development/production) | No |
| `GOOGLE_OAUTH_CLIENT_ID` | Google OAuth client ID | No |
| `GOOGLE_OAUTH_CLIENT_SECRET` | Google OAuth client secret | No |

## File Structure

```
Goal-tracker/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── vercel.json           # Vercel deployment configuration
├── .env.example          # Environment variables template
├── .gitignore           # Git ignore rules
├── demo/                # Demo video and assets
│   ├── project-demo.gif # Animated demo (GitHub README display)
│   └── video.mp4        # Full quality demonstration video
├── static/
│   └── style.css        # Application styles
├── templates/           # Jinja2 templates
│   ├── base.html
│   ├── index.html
│   ├── analytics.html
│   ├── settings.html
│   └── ...
└── instance/
    └── todo_app.db      # Local SQLite database (development only)
```

## Technology Stack

- **Backend**: Flask, Python
- **Database**: MongoDB (PyMongo)
- **Frontend**: HTML5, CSS3, JavaScript
- **Charts**: Chart.js
- **Authentication**: Flask-Login
- **PDF Generation**: ReportLab
- **Deployment**: Vercel
- **Demo Assets**: MP4 video + Optimized GIF (FFmpeg conversion)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test locally
5. Submit a pull request

## License

This project is licensed under the MIT License.

## Support

For issues and questions:
- Create an issue on GitHub
- Check the documentation
- Review the environment setup

---

**Happy Goal Tracking! 🎯**
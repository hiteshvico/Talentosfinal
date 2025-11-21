# TalentOS - AI-Powered Career Development Platform

<div align="center">
  
  ![TalentOS](https://img.shields.io/badge/TalentOS-Career%20Development-blueviolet)
  ![React](https://img.shields.io/badge/React-18.x-blue)
  ![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue)
  ![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.0-06B6D4)
  ![Google Cloud](https://img.shields.io/badge/Google%20Cloud-Platform-4285F4)
  ![Cloud Run](https://img.shields.io/badge/Cloud%20Run-Serverless-4285F4)
  ![License](https://img.shields.io/badge/license-MIT-green)

  **An intelligent upskilling platform that empowers students, freshers, and professionals through AI-driven career guidance, personalized learning paths, and expert mentorship.**
  
  **Built on Google Cloud Platform with Cloud Run, Gemini AI, and scalable cloud infrastructure.**

  [Features](#-key-features) • [Demo](#-demo) • [Installation](#-installation) • [Architecture](#-architecture) • [Tech Stack](#-tech-stack) • [Contributing](#-contributing)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Deployment](#-deployment)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [User Flows](#-user-flows)
- [Screenshots](#-screenshots)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

**TalentOS** is a modern, intuitive web platform designed to revolutionize career development and upskilling. The platform leverages AI to provide personalized career recommendations, interactive learning roadmaps, and connects users with expert mentors to accelerate their professional growth.

### Who is it for?

- 🎓 **Students** exploring career options
- 🚀 **Fresh Graduates** entering the job market
- 💼 **Working Professionals** looking to upskill or pivot careers
- 🏢 **Enterprises** managing employee development programs

---

## ✨ Key Features

### 🤖 AI-Powered Career Discovery
- **Interactive Career Chat Assistant** with contextual recommendations
- **Smart Career Path Detection** based on user interests and experience
- **Personalized Course Recommendations** for specific technologies (Vibe coding, Cloud Run, Gemini CLI, etc.)
- **Real-time AI Conversations** with career guidance

### 📚 Personalized Learning Roadmaps
- **Dynamic Learning Paths** tailored to chosen careers (Product Manager, Full Stack Developer, UX Designer, etc.)
- **Gamified Progress Tracking** with badges, streaks, and milestones
- **Three Skill Levels**: Beginner → Intermediate → Pro
- **Interactive Course Cards** with completion tracking
- **Visual Milestones** showing career progression

### 👥 Expert Mentorship Network
- **Internal Company Mentors** (e.g., Google mentors)
- **External Industry Experts** from YouTube, LinkedIn Learning, etc.
- **Real-time Booking System** with calendar integration
- **Session Management** with feedback history
- **Video & Chat Sessions** support

### 🏢 Enterprise Dashboard
- **Admin Dashboard** with credential-based authentication (admin / admin)
- **Manager Dashboard** for team oversight and analytics
- **Employee Dashboard** with personalized learning insights
- **Real-time Analytics** on skill development and progress
- **Team Performance Tracking**

### 🎮 Gamification Elements
- **Achievement Badges** (First Steps, Learning Streak, Course Master, etc.)
- **Daily Streaks** to encourage consistent learning
- **Progress Tracking** across different skill levels
- **Milestone Celebrations** with visual feedback

### 🎨 Modern UI/UX
- **Clean, Minimal Design** inspired by Notion, Duolingo, and Coursera
- **Soft Gradients** and friendly color palettes
- **Responsive Design** for mobile and desktop
- **Smooth Animations** and loading screens
- **Intuitive Navigation** with role-based access control

---

## 🏗 Architecture

TalentOS is built on a modern, scalable cloud-native architecture leveraging Google Cloud Platform services for maximum performance and reliability.

### System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                          Frontend Layer                          │
│  React 18 + TypeScript + Tailwind CSS (Deployed on Cloud Run)   │
└────────────────────────┬────────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────────┐
│                        API Gateway Layer                         │
│              Cloud Run Services (Auto-scaling)                   │
│  • Authentication Service                                        │
│  • Career Discovery API                                          │
│  • Learning Roadmap API                                          │
│  • Mentor Booking API                                            │
│  • Analytics API                                                 │
└────────────┬────────────────────────────┬──────────────────────┘
             │                            │
             ▼                            ▼
┌────────────────────────────┐  ┌────────────────────────────────┐
│   Gemini AI Services       │  │    Database Layer              │
│  • Gemini Pro API          │  │  • Cloud SQL (PostgreSQL)      │
│  • Gemini CLI Integration  │  │    - User profiles             │
│  • NLP Processing          │  │    - Learning progress         │
│  • Career Recommendations  │  │    - Mentor sessions           │
│  • Chat Assistant          │  │    - Analytics data            │
└────────────────────────────┘  │  • Cloud Firestore             │
                                │    - Real-time chat            │
                                │    - Notifications             │
                                └───────────┬────────────────────┘
                                            │
                                            ▼
                                ┌───────────────────────────────┐
                                │   Cloud Storage               │
                                │  • Course materials           │
                                │  • User avatars               │
                                │  • Media assets               │
                                └───────────────────────────────┘
```

### Key Architecture Decisions

1. **Serverless-First Approach**: Cloud Run enables automatic scaling based on traffic, reducing infrastructure costs and management overhead.

2. **Microservices Design**: Each major feature (authentication, career discovery, learning paths, mentorship) runs as an independent Cloud Run service for better scalability and maintainability.

3. **AI-Powered Intelligence**: Gemini Pro API and Gemini CLI provide contextual career guidance, understanding complex queries like "I want to learn Vibe coding" or "How do I use Cloud Run for deployment?"

4. **Database Strategy**:
   - **Cloud SQL (PostgreSQL)** for relational data requiring ACID compliance
   - **Cloud Firestore** for real-time features like chat and live notifications
   - **Cloud Storage** for blob storage (images, videos, documents)

5. **CI/CD Pipeline**: Cloud Build automatically deploys code changes to Cloud Run, ensuring zero-downtime deployments.

### Data Flow

1. **User Onboarding**: Form data → Gemini AI analysis → Career path detection → Cloud SQL storage
2. **AI Chat**: User message → Gemini Pro API → Contextual response → Firestore sync
3. **Learning Progress**: Course completion → Cloud SQL update → Badge calculation → Real-time UI update
4. **Mentor Booking**: Session request → Cloud SQL transaction → Notification trigger → Email/Push notification

---

## 🛠 Tech Stack

### Frontend
- **React 18.x** - UI framework
- **TypeScript** - Type safety
- **Tailwind CSS 4.0** - Styling and design system
- **Lucide React** - Modern icon library
- **Motion/React** - Smooth animations

### Backend & Infrastructure
- **Google Cloud Platform (GCP)** - Cloud infrastructure
- **Cloud Run** - Serverless container deployment for scalable backend services
- **Cloud SQL (PostgreSQL)** - Managed relational database for user data, learning progress, and analytics
- **Gemini AI API** - Advanced AI for career recommendations and chat assistant
- **Gemini CLI** - Command-line tools for AI model integration and deployment
- **Cloud Storage** - Media and asset storage
- **Cloud Functions** - Serverless compute for event-driven tasks

### AI & Machine Learning
- **Gemini Pro API** - Contextual career guidance and course recommendations
- **Natural Language Processing** - Understanding user queries about Vibe coding, Cloud Run, Gemini CLI, etc.
- **Personalization Engine** - AI-driven learning path customization

### Database & Storage
- **Cloud SQL (PostgreSQL)** - Primary database for:
  - User profiles and authentication
  - Learning progress and achievements
  - Mentor session bookings and feedback
  - Enterprise analytics and reporting
- **Cloud Firestore** - Real-time data synchronization for chat and notifications
- **Cloud Storage** - Course materials, user avatars, and media assets

### UI Components
- Custom component library built with Radix UI primitives
- Reusable components: Button, Card, Badge, Calendar, Tabs, etc.
- UserMenu with avatar and dropdown functionality

### State Management
- React Hooks (useState, useEffect)
- Context-aware state handling for user profiles
- Persistent career path caching

### DevOps & Deployment
- **Cloud Build** - CI/CD pipeline for automated deployments
- **Container Registry** - Docker image storage
- **Cloud Run** - Automatic scaling and zero-downtime deployments
- **Cloud Monitoring** - Performance tracking and error logging
- **Cloud IAM** - Secure access control and authentication

### Key Libraries
- `react-hook-form@7.55.0` - Form handling
- `recharts` - Data visualization
- `date-fns` - Date formatting
- `sonner` - Toast notifications
- `@google-cloud/storage` - GCP Storage SDK
- `pg` - PostgreSQL client for Node.js

---

## 🚀 Installation

### Prerequisites
- Node.js 18.x or higher
- npm or yarn package manager

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/hiteshvico/Talentosfinal.git
   cd talentos
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start the development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

4. **Open your browser**
   ```
   Navigate to http://localhost:5173
   ```

---

## 🚢 Deployment

TalentOS is designed to be deployed on Google Cloud Platform using Cloud Run for serverless, scalable deployment.

### Deployment to Cloud Run

#### Prerequisites
- Google Cloud Platform account
- `gcloud` CLI installed and configured
- Docker installed locally
- Project set up in GCP with billing enabled

#### Step 1: Set up GCP Project

```bash
# Set your project ID
export PROJECT_ID="your-project-id"
gcloud config set project $PROJECT_ID

# Enable required APIs
gcloud services enable run.googleapis.com
gcloud services enable cloudbuild.googleapis.com
gcloud services enable sqladmin.googleapis.com
gcloud services enable storage-api.googleapis.com
gcloud services enable aiplatform.googleapis.com
```

#### Step 2: Set up Cloud SQL (PostgreSQL)

```bash
# Create Cloud SQL instance
gcloud sql instances create talentos-db \
  --database-version=POSTGRES_15 \
  --tier=db-f1-micro \
  --region=us-central1

# Create database
gcloud sql databases create talentos --instance=talentos-db

# Create database user
gcloud sql users create talentos-user \
  --instance=talentos-db \
  --password=your-secure-password
```

#### Step 3: Set up Gemini AI API

```bash
# Enable Vertex AI API for Gemini
gcloud services enable aiplatform.googleapis.com

# Set up Gemini CLI credentials
export GEMINI_API_KEY="your-gemini-api-key"

# Test Gemini CLI
gemini --version
```

#### Step 4: Build and Deploy Frontend to Cloud Run

```bash
# Build the Docker image
gcloud builds submit --tag gcr.io/$PROJECT_ID/talentos-frontend

# Deploy to Cloud Run
gcloud run deploy talentos-frontend \
  --image gcr.io/$PROJECT_ID/talentos-frontend \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated \
  --memory 512Mi \
  --cpu 1 \
  --min-instances 0 \
  --max-instances 10
```

#### Step 5: Set up Environment Variables

```bash
# Set environment variables for Cloud Run service
gcloud run services update talentos-frontend \
  --set-env-vars="DATABASE_URL=your-cloud-sql-connection-string" \
  --set-env-vars="GEMINI_API_KEY=your-gemini-api-key" \
  --set-env-vars="CLOUD_STORAGE_BUCKET=your-bucket-name"
```

#### Step 6: Set up Cloud Storage

```bash
# Create bucket for course materials and media
gsutil mb -p $PROJECT_ID -c STANDARD -l us-central1 gs://talentos-assets

# Set CORS configuration for web access
cat > cors.json <<EOF
[
  {
    "origin": ["*"],
    "method": ["GET", "HEAD"],
    "responseHeader": ["Content-Type"],
    "maxAgeSeconds": 3600
  }
]
EOF

gsutil cors set cors.json gs://talentos-assets
```

#### Step 7: Set up CI/CD with Cloud Build

Create `cloudbuild.yaml`:

```yaml
steps:
  # Build the container image
  - name: 'gcr.io/cloud-builders/docker'
    args: ['build', '-t', 'gcr.io/$PROJECT_ID/talentos-frontend', '.']
  
  # Push the container image to Container Registry
  - name: 'gcr.io/cloud-builders/docker'
    args: ['push', 'gcr.io/$PROJECT_ID/talentos-frontend']
  
  # Deploy to Cloud Run
  - name: 'gcr.io/google.com/cloudsdktool/cloud-sdk'
    entrypoint: gcloud
    args:
      - 'run'
      - 'deploy'
      - 'talentos-frontend'
      - '--image'
      - 'gcr.io/$PROJECT_ID/talentos-frontend'
      - '--region'
      - 'us-central1'
      - '--platform'
      - 'managed'

images:
  - 'gcr.io/$PROJECT_ID/talentos-frontend'
```

Set up automatic deployments:

```bash
# Connect your GitHub repository to Cloud Build
gcloud builds triggers create github \
  --repo-name=talentos \
  --repo-owner=your-github-hiteshvico \
  --branch-pattern="^main$" \
  --build-config=cloudbuild.yaml
```

### Database Migration

```bash
# Connect to Cloud SQL
gcloud sql connect talentos-db --user=talentos-user

# Run migrations (example)
psql -d talentos -f migrations/001_initial_schema.sql
```

### Monitoring and Logging

```bash
# View Cloud Run logs
gcloud run services logs read talentos-frontend --limit=50

# Set up Cloud Monitoring alerts
gcloud alpha monitoring policies create \
  --notification-channels=YOUR_CHANNEL_ID \
  --display-name="TalentOS High Error Rate" \
  --condition-display-name="Error rate > 5%" \
  --condition-threshold-value=5
```

### Cost Optimization

- **Cloud Run**: Scales to zero when not in use, only pay for actual usage
- **Cloud SQL**: Use `db-f1-micro` for development, scale up for production
- **Gemini API**: Monitor API usage and implement caching for common queries
- **Cloud Storage**: Use lifecycle policies to archive old content

### Production Checklist

- [ ] Set up custom domain with Cloud Run
- [ ] Enable Cloud CDN for static assets
- [ ] Configure Cloud Armor for DDoS protection
- [ ] Set up Cloud IAM roles and permissions
- [ ] Enable Cloud Monitoring and Error Reporting
- [ ] Configure backup strategy for Cloud SQL
- [ ] Set up Cloud Scheduler for maintenance tasks
- [ ] Enable SSL/TLS certificates
- [ ] Configure Cloud Load Balancing (if using multiple regions)

---

## 📖 Usage

### Getting Started

1. **Landing Page**
   - Click "Get Started" to begin your journey
   - Fill out the onboarding form with your education, experience, and interests
   - Get AI-powered career path recommendations

2. **Career Discovery**
   - Explore different career paths (Product Manager, Full Stack Developer, UX Designer, etc.)
   - View curated course recommendations for each path
   - Use the AI Chat Assistant for personalized guidance

3. **Learning Roadmap**
   - View your personalized learning path
   - Track progress across Beginner, Intermediate, and Pro levels
   - Complete courses and unlock achievements
   - Monitor your daily streaks and milestones

4. **Mentor Sessions**
   - Browse internal company mentors and external experts
   - Book 1-on-1 sessions with calendar integration
   - View session history and mentor feedback

5. **Enterprise Features**
   - **Admin Login**: admin@kore.com / admin123
   - **Manager Login**: manager@kore.com / manager123
   - **Employee View**: Accessible from user menu → "My Dashboard"

---

## 📁 Project Structure

```
talentos/
├── src/
│   ├── App.tsx                          # Main application component
│   ├── components/
│   │   ├── LandingPage.tsx             # Landing and onboarding
│   │   ├── CareerDiscovery.tsx         # Career path exploration
│   │   ├── CareerChatAssistant.tsx     # AI chat interface
│   │   ├── LearningRoadmap.tsx         # Personalized learning dashboard
│   │   ├── LearningRoadmapData.tsx     # Course and milestone data
│   │   ├── MentorPage.tsx              # Mentor booking system
│   │   ├── AdminDashboard.tsx          # Enterprise admin panel
│   │   ├── EmployeeDashboard.tsx       # Employee view
│   │   ├── LoadingScreen.tsx           # Animated transitions
│   │   ├── UserMenu.tsx                # User profile dropdown
│   │   ├── ui/                         # Reusable UI components
│   │   │   ├── button.tsx
│   │   │   ├── card.tsx
│   │   │   ├── badge.tsx
│   │   │   ├── input.tsx
│   │   │   ├── calendar.tsx
│   │   │   ├── tabs.tsx
│   │   │   └── ...
│   │   └── figma/
│   │       └── ImageWithFallback.tsx   # Image component with fallback
│   └── styles/
│       └── globals.css                  # Global styles and design tokens
├── package.json
└── README.md
```

---

## 🔄 User Flows

### 1. New User Onboarding
```
Landing Page → Fill Form → AI Processing → Loading Screen → Personalized Roadmap
```

### 2. Career Exploration
```
Landing Page → Career Discovery → Browse Paths → Select Career → Loading Screen → Roadmap
```

### 3. AI Chat Journey
```
Landing Page → Chat with AI → Discuss Interests → Get Recommendations → View Roadmap
```

### 4. Mentor Booking
```
Roadmap → Book Mentor → Browse Mentors → Select Date/Time → Request Session → Success Modal
```

### 5. Enterprise Access
```
Landing Page → Admin Login → Dashboard → View Analytics → Employee Details → Manager Insights
```

---

## 📸 Screenshots

### 🏠 Landing Page
Clean, modern landing page with AI-powered onboarding form

### 🎯 Career Discovery
Explore various career paths with AI-curated course recommendations

### 💬 AI Chat Assistant
Interactive chat interface with contextual career guidance

### 📚 Learning Roadmap
Gamified dashboard with progress tracking, badges, and milestones

### 👨‍🏫 Mentor Network
Browse and book sessions with internal and external mentors

### 📊 Admin Dashboard
Enterprise analytics with employee progress tracking

---

## 🗺 Roadmap

### Current Features ✅
- [x] AI-powered career discovery
- [x] Interactive chat assistant with contextual recommendations
- [x] Personalized learning roadmaps
- [x] Gamification (badges, streaks, milestones)
- [x] Mentor booking system
- [x] Enterprise admin dashboard
- [x] Role-based access control
- [x] User profile management

### Upcoming Features 🚧
- [ ] Backend integration with Supabase
- [ ] Real-time notifications
- [ ] Advanced analytics and reporting
- [ ] Mobile app (React Native)
- [ ] Integration with learning platforms (Coursera, Udemy, etc.)
- [ ] Video call integration for mentor sessions
- [ ] Community forums and peer learning
- [ ] Certificate generation
- [ ] Skill assessments and quizzes
- [ ] LinkedIn integration for profile sync

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Development Guidelines

- Follow the existing code style and conventions
- Write meaningful commit messages
- Add comments for complex logic
- Test your changes thoroughly
- Update documentation as needed

### Bug Reports

Found a bug? Please open an issue with:
- Clear description of the problem
- Steps to reproduce
- Expected vs actual behavior
- Screenshots (if applicable)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Design inspiration from Notion, Duolingo, and Coursera
- Icons by [Lucide Icons](https://lucide.dev/)
- Images from [Unsplash](https://unsplash.com/)
- UI components built with [Radix UI](https://www.radix-ui.com/)

---

## 📧 Contact

Have questions or suggestions? Reach out to us!

- **Project Link**: [https://github.com/yourhiteshvico/Talentosfinal](https://github.com/yourhiteshvico/talentos)
- **Issues**: [https://github.com/yourhiteshvico/Talentosfinal/issues](https://github.com/yourhiteshvico/talentos/issues)
- **Email**: krathi@180dc.org
---

<div align="center">
  
  **Made with ❤️ for the future of learning**
  
  ⭐ Star this repo if you find it useful!
  
</div>


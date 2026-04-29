# CodeTrail 🚀

<div align="center">
  <img src="Client/public/favicon.svg" alt="CodeTrail Logo" width="80" height="80">
  <h3>AI-Powered Competitive Programming Tracker</h3>
  <p>Track your coding journey across multiple platforms with intelligent insights and personalized AI coaching</p>
  
  ![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
  ![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
  ![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
  ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
  ![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
</div>

## ✨ What Makes CodeTrail Special

CodeTrail is not just another coding tracker. It's an **AI-powered competitive programming companion** that reverse-engineers platform APIs to provide unified analytics, personalized coaching, and intelligent insights that help you become a better programmer.

### 🎯 Core Features

- **🤖 AI Coach**: Get personalized recommendations based on your actual coding patterns and weak areas
- **📊 Unified Analytics**: Track progress across LeetCode, Codeforces, and other platforms in one dashboard
- **⚡ Smart Caching**: Redis-powered caching delivers sub-50ms response times with 80% fewer API calls
- **🎨 Adaptive UI**: Beautiful dark/light themes with platform-specific visualizations
- **📈 Visual Analytics**: Interactive charts, heatmaps, and progress tracking with real-time updates

## 🚀 Live Demo

**Frontend**: [CodeTrail Dashboard](https://main.d2jc37kgdt0gqz.amplifyapp.com/)  
**Backend API**: [CodeTrail API](https://codetrail-backend.railway.app)

> **Note**: Create an account and connect your coding platforms to see the full power of AI-driven analytics!

## 📸 Screenshots

<div align="center">
  <img src="Client/src/assets/dashboard-overview-dark.png" alt="Dashboard Overview" width="45%">
  <img src="Client/src/assets/ai-analysis-dark.png" alt="AI Analysis" width="45%">
</div>

## 🛠️ Tech Stack

### Frontend
- **React 18** with TypeScript for type safety
- **Vite** for lightning-fast development
- **Tailwind CSS** + **shadcn/ui** for beautiful, consistent UI
- **Recharts** for interactive data visualizations
- **TanStack Query** for smart data fetching and caching

### Backend
- **Node.js** + **Express.js** for robust API development
- **PostgreSQL** with **Prisma ORM** for type-safe database operations
- **Redis** for intelligent caching and session management
- **JWT** authentication with refresh token rotation
- **Deepseek LLM** for AI-powered coaching and insights

### Infrastructure
- **AWS Amplify** for frontend hosting with CI/CD
- **Railway** for backend deployment with auto-scaling
- **PostgreSQL** and **Redis** managed services
- **GitHub Actions** for automated testing and deployment

## 🏗️ Architecture

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   React SPA     │────│   Express API    │────│   PostgreSQL    │
│   (Amplify)     │    │   (Railway)      │    │   (Primary DB)  │
└─────────────────┘    └──────────────────┘    └─────────────────┘
         │                       │                       │
         │              ┌──────────────────┐             │
         └──────────────│   Redis Cache    │─────────────┘
                        │   (Session +     │
                        │   Performance)   │
                        └──────────────────┘
                                 │
                   ┌─────────────────────────────────┐
                   │        External APIs            │
                   │  LeetCode • Codeforces • AI     │
                   └─────────────────────────────────┘
```



## 🎯 Key Features Implementation

### 1. **Reverse-Engineered APIs**
```typescript
// Smart GraphQL integration for platforms without public APIs
const getUserProfile = async (username: string) => {
  const query = `
    query getUserProfile($username: String!) {
      matchedUser(username: $username) {
        profile { reputation, ranking }
        submissionCalendar
        submitStats { acSubmissionNum }
      }
    }
  `;
  return await graphqlClient.request(query, { username });
};
```

### 2. **Intelligent Caching Strategy**
```typescript
// Different TTL for different data types
const cacheStrategies = {
  userProfiles: 300,      // 5 minutes
  calendarData: 3600,     // 1 hour  
  contestRankings: 900,   // 15 minutes
  staticProblems: 86400,  // 24 hours
  aiContext: 1800         // 30 minutes
};
```

### 3. **AI-Powered Insights**
```typescript
// Context-aware recommendations based on user data
const generateRecommendations = async (userData: UserAnalysis) => {
  const context = `
    User has solved ${userData.totalProblems} problems.
    Weak areas: ${userData.weakTopics.join(', ')}
    Recent activity: ${userData.recentSubmissions}
  `;
  return await aiService.generateInsights(context);
};
```

### Development Guidelines
- Write TypeScript for type safety
- Follow the existing code style and patterns
- Add tests for new features
- Update documentation as needed

## 📝 API Documentation

### Authentication Endpoints
```http
POST /api/auth/register    # User registration
POST /api/auth/login       # User login
POST /api/auth/refresh     # Refresh access token
POST /api/auth/logout      # User logout
```

### Platform Integration
```http
GET  /api/platforms/connect/:platform    # Connect coding platform
GET  /api/dashboard/stats                # Get unified dashboard data
GET  /api/analytics/detailed             # Get detailed analytics
POST /api/ai-coach/analyze               # Get AI-powered insights
```

See the [full API documentation](Server/src/routes) for detailed endpoint specifications.

## 🔒 Security Features

- **JWT Authentication** with refresh token rotation
- **Rate Limiting** to prevent API abuse
- **Input Validation** using Joi schemas
- **CORS Configuration** for secure cross-origin requests
- **Helmet.js** for security headers
- **Environment-based Configuration** for different deployment stages

## 📈 Performance Optimizations

- **Redis Caching**: 80% reduction in external API calls
- **Intelligent Data Fetching**: Parallel requests with smart fallbacks
- **Code Splitting**: Lazy loading for better initial load times
- **Image Optimization**: Responsive images with proper formats
- **Database Indexing**: Optimized queries for fast data retrieval

## 🐛 Troubleshooting

### Common Issues

**Problem**: Database connection errors  
**Solution**: Ensure PostgreSQL is running and DATABASE_URL is correct

**Problem**: Redis connection failed  
**Solution**: The app works without Redis (graceful fallback), but performance will be slower

**Problem**: External API rate limits  
**Solution**: Implement exponential backoff and respect platform rate limits


---

<div align="center">
  <p>Built with ❤️ for the competitive programming community</p>
</div>

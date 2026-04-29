# CodeLens - AI-Powered Coding Tracker

Track your coding journey across multiple platforms with AI-powered insights and personalized recommendations.

## 🚀 Features

- **Multi-Platform Integration**: Connect LeetCode, Codeforces, and other coding platforms
- **AI-Powered Coaching**: Get personalized recommendations based on your coding patterns
- **Unified Analytics**: View your progress across all platforms in one dashboard
- **Smart Caching**: Optimized performance with Redis-powered caching
- **Real-time Insights**: Track contest ratings, submission patterns, and topic mastery
- **Dark/Light Theme**: Adaptive theming with system preference detection

## 🛠️ Tech Stack

### Frontend
- **React 18** with TypeScript
- **Vite** for fast development
- **Tailwind CSS** + **shadcn/ui** for styling
- **Recharts** for data visualization
- **React Context** for state management

### Backend
- **Node.js** + **Express.js**
- **PostgreSQL** with **Prisma ORM**
- **Redis** for caching
- **JWT** authentication
- **Deepseek LLM** for AI coaching

## 🏗️ Architecture

- **Client-Server Architecture** with REST APIs
- **Reverse-engineered GraphQL** integration for LeetCode data
- **Intelligent caching strategy** with different TTL for various data types
- **Microservices-style organization** with dedicated controllers and services



## 🔧 Key Features Implementation

### LeetCode Integration
- Reverse-engineered GraphQL API for data access
- Smart rate limiting and error handling
- Comprehensive user profile and submission data

### AI Coaching System
- Powered by Deepseek LLM
- Context-aware recommendations
- Personalized problem suggestions based on weak areas

### Caching Strategy
- **User Profiles**: 5min TTL
- **Calendar Data**: 1hr TTL  
- **Contest Rankings**: 15min TTL
- **Static Problems**: 24hr TTL
- **AI Context**: 30min TTL



Built with ❤️ for the competitive programming community

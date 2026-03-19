# 🏃‍♂️ FitSync - Smart Fitness Companion

> A comprehensive fitness tracking and AI-powered health assistant built for **BitsNBuild Hackathon**

## 📊 Project Overview

FitSync is an intelligent fitness application that integrates with smartwatches and fitness bands to provide personalized health insights, meal planning, and fitness recommendations using advanced AI technology. The app helps users track their daily activities, analyze their fitness data, and receive customized suggestions to achieve their health goals.

## 👥 Team: **Class_Bunkers**

- **Divya Ratna Gautam** - Frontend Developer & Team Lead  
- **Vishesh Sachan** - Backend & Integration
- **Nazeeb Warsi** - Frontend  & Integration
- **Abhijeet Gupta** - Backend Developer & GenAI Developer

*Participating in: **BitsNBuild Hackathon***

## 🛠️ Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js v4** - Web framework
- **Prisma ORM** - Database management
- **PostgreSQL** - Primary database
- **JWT** - Authentication
- **bcryptjs** - Password hashing

### AI & Machine Learning
- **LangChain** - AI framework
- **OpenAI GPT-3.5** - Language model
- **Google Gemini 2.0** - Alternative AI model
- **Zod** - Schema validation and output parsing

### Development Tools
- **Nodemon** - Development server
- **dotenv** - Environment configuration

## 🚀 Features

### 🔐 Authentication System
- User registration and login
- JWT-based authentication
- Secure password hashing
- Protected routes

### 📱 User Management
- Complete user profiles with health metrics
- BMI calculation and categorization
- Target weight goal setting
- Activity level tracking

### 📊 Health Analytics
- Daily stats tracking (steps, calories, heart rate, sleep)
- BMI analysis with health recommendations
- Calorie burn calculation for various activities
- AI-powered fitness suggestions

### 🍽️ Nutrition Tracking
- Daily meal logging (breakfast, lunch, dinner, snacks)
- Nutritional breakdown analysis
- AI-generated meal plan suggestions
- Date-wise meal history

### 🏃‍♂️ Fitness Events
- Create and manage fitness events
- Event registration system
- Event discovery and filtering
- Organizer dashboard

### 🤖 AI Chat Assistant
- Fitness and health Q&A
- Personalized recommendations based on user data
- Strict topic filtering (fitness/health only)
- Context-aware responses using user's daily stats and meals

## 📁 Project Structure

```
bitnbuild_backend/
├── src/
│   └── users/
│       ├── user.js          # User authentication & management
│       ├── stats.js         # Health analytics & AI suggestions
│       ├── dashboard.js     # Dashboard data endpoints
│       └── events.js        # Fitness events management
├── middleware/
│   └── userMiddleware.js    # Authentication & validation
├── prisma/
│   ├── schema.prisma        # Database schema
│   └── migrations/          # Database migrations
├── index.js                 # Main server file
├── package.json
└── .env                     # Environment variables
```

## 📚 API Endpoints

### Authentication
- `POST /api/users/register` - User registration
- `POST /api/users/login` - User login
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/update` - Update user information

### Health & Analytics
- `POST /api/stats/bmi` - BMI calculation and health suggestions
- `POST /api/stats/activity` - Activity calorie calculation
- `POST /api/stats/weight-goal` - Weight goal planning
- `POST /api/stats/meal` - Meal logging and analysis
- `GET /api/stats/meals` - Get all meal history
- `GET /api/stats/meals/:date` - Get meals by date
- `POST /api/stats/chat` - AI fitness assistant

### Dashboard
- `GET /api/dashboard/getdailystats` - Get/generate daily stats

### Events
- `POST /api/events/create` - Create fitness event
- `GET /api/events` - List all events
- `GET /api/events/:id` - Get specific event
- `PUT /api/events/:id` - Update event (creator only)
- `POST /api/events/:id/register` - Register for event
- `DELETE /api/events/:id/unregister` - Unregister from event
- `GET /api/events/my/created` - Get user's created events
- `GET /api/events/my/registered` - Get user's registered events

## 🔧 Installation & Setup

### Prerequisites
- Node.js (v18 or higher)
- PostgreSQL database
- OpenAI API key
- Google API key (for Gemini)

### 1. Clone the Repository
```bash
git clone https://github.com/ag21o9/bitnbuild_backend.git
cd bitnbuild_backend
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Environment Configuration
Create a `.env` file in the root directory:
```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/fitsync_db?schema=public"

# API Keys
OPENAI_API_KEY="your_openai_api_key_here"
GOOGLE_API_KEY="your_google_api_key_here"

# JWT Secret
JWT_SECRET="your_super_secure_jwt_secret_key"

# Server
PORT=3000
```

### 4. Database Setup
```bash
# Generate Prisma client
npx prisma generate

# Push schema to database
npx prisma db push

# (Optional) Open Prisma Studio to view data
npx prisma studio
```

### 5. Run the Application
```bash
# Development mode
npm run dev

# Production mode
npm start
```

The server will start on `http://localhost:3000`

## 🧪 Testing the API

### Register a new user:
```bash
curl -X POST http://localhost:3000/api/users/register \
  -H "Content-Type: application/json" \
  -d '{
    "name": "John Doe",
    "email": "john@example.com",
    "password": "password123",
    "age": 28,
    "heightCm": 180,
    "currentWeightKg": 75,
    "gender": "MALE",
    "healthGoal": "WEIGHT_LOSS",
    "activityLevel": "MODERATE"
  }'
```

### Get daily stats:
```bash
curl -X GET http://localhost:3000/api/dashboard/getdailystats \
  -H "Authorization: Bearer YOUR_JWT_TOKEN"
```

### Chat with AI assistant:
```bash
curl -X POST http://localhost:3000/api/stats/chat \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_JWT_TOKEN" \
  -d '{
    "message": "What should I eat after my workout?"
  }'
```

## 🔮 Future Scope

### 📱 Mobile Integration
- React Native mobile app
- Real-time sync with fitness devices
- Push notifications for goals and reminders

### 🏥 Advanced Health Features
- Integration with health monitoring devices
- Medication reminders and tracking
- Doctor appointment scheduling
- Health report generation

### 🤝 Social Features
- Friend connections and challenges
- Community fitness groups
- Achievement badges and leaderboards
- Social sharing of progress

### 🧠 Enhanced AI Capabilities
- Computer vision for exercise form correction
- Voice-activated fitness assistant
- Predictive health analytics
- Personalized workout video generation

### 📈 Analytics & Insights
- Advanced progress visualization
- Machine learning-based trend analysis
- Comparative health metrics
- Goal prediction algorithms

### 🌐 Platform Expansion
- Web dashboard
- Smartwatch applications
- Integration with popular fitness apps
- API marketplace for third-party developers

## 🏆 Hackathon Achievement

Built during **BitsNBuild Hackathon** by Team **Class_Bunkers**, demonstrating:
- Full-stack development expertise
- AI/ML integration capabilities
- Database design and management
- RESTful API development
- Authentication and security implementation

## 📄 License

This project is developed for BitsNBuild Hackathon and is proprietary to Team Class_Bunkers.

## 🤝 Contributing

This project was developed for a hackathon. For any inquiries or collaboration opportunities, please contact the team members.

---

*Built with ❤️ by Team Class_Bunkers for BitsNBuild Hackathon 2025*

# 🤖 AI News Aggregator

A full-stack web application that aggregates news from multiple sources and provides personalized feeds with AI-generated summaries.

## ✨ Features

- **User Authentication** - Secure JWT-based login/register system
- **Personalized Feed** - Get news based on your selected interests
- **AI Summaries** - Grok-3 powered 100-word article summaries
- **Auto-Updates** - Daily news fetch at 6:30 PM IST
- **8 Categories** - Technology, Business, Entertainment, Environment, Finance, Smart Home, Social Media, Retail

## 🛠️ Tech Stack

**Backend:** Node.js, Express.js, MongoDB, Mongoose  
**Frontend:** React 19, Vite, Context API  
**APIs:** GNews API, Grok-3 AI  
**Auth:** JWT, bcrypt  
**Scheduling:** node-cron

## 📁 Project Structure

```
AI_NEWS_AGGREGATOR/
├── Backend/
│   ├── app.js
│   ├── server.js
│   ├── controllers/
│   ├── routes/
│   ├── models/
│   └── services/
└── Frontend/
    ├── index.html
    └── context/
```

## 🚀 Quick Start

### Backend Setup

```bash
cd Backend
npm install
```

Create `.env` file:
```env
PORT=3000
DB_CONNECT=mongodb://localhost:27017/news_aggregator
JWT_SECRET=your_secret_key
NEWS_API_KEY=your_gnews_api_key
GROK_API_KEY=your_grok_api_key
```

Run server:
```bash
npm start
```

### Frontend Setup

```bash
cd Frontend
npm install
npm run dev
```

## 🔌 API Endpoints

| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| POST | `/user/register` | No | Register new user |
| POST | `/user/login` | No | Login user |
| GET | `/user/profile` | Yes | Get user profile |
| PUT | `/user/update` | Yes | Update profile |
| POST | `/user/logout` | Yes | Logout user |
| GET | `/user/news` | Yes | Get personalized news |

## 📝 Register/Login Body

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securepass123",
  "categories": ["Technology", "Business"]
}
```

## 🤖 AI Summarization

- Runs daily at **6:30 PM IST**
- Fetches latest articles from GNews
- Uses **Grok-3** to generate summaries
- Manual run: `node Backend/run-article-job.js`

## 🔒 Security

- ✅ Password hashing (bcrypt)
- ✅ JWT authentication
- ✅ Token blacklisting on logout
- ✅ HTTP-only cookies
- ✅ Input validation

## 📦 Database Models

**User:** name, email, password, categories  
**Article:** heading, picture, author, website_url, description, categories, publishedAt

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first.

## 📄 License

MIT

---

**Made with ❤️ by [Your Name]**

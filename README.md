# 🚨 Warcast.app - Real-time Global Conflict Intelligence Platform

<div align="center">
  [![Live Demo](https://img.shields.io/badge/Live-Demo-red?style=for-the-badge)](https://warcast.app)
  [![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
  [![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
  [![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org/)
  [![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
</div>

## 🌍 About

Warcast.app is an advanced real-time conflict monitoring system that aggregates, analyzes, and visualizes global military conflicts using cutting-edge AI/ML technologies. In an era of information overload and rapidly evolving global tensions, our platform provides clarity by:

- 📰 **Aggregating news from 25+ trusted sources** every 3 minutes
- 🤖 **AI-powered analysis** using OpenAI GPT-4 for hourly intelligence briefs
- 🎯 **Threat assessment** with our proprietary WW3 Doomsday Clock algorithm
- 🗺️ **Geographic visualization** of conflict zones and events
- 📊 **Sentiment analysis** and trend tracking over time

## ✨ Key Features

### Real-time Intelligence
- **3-minute news cycle** - Constantly updated from BBC, CNN, Al Jazeera, Reuters, and 20+ sources
- **Duplicate detection** - Smart grouping of similar stories across sources
- **Multi-language support** - Processes news in multiple languages

### AI-Powered Analysis
- **Hourly Intelligence Briefs** - GPT-4 powered summaries of global conflict sentiment
- **Entity Extraction** - Identifies countries, organizations, weapons, and key figures
- **Threat Scoring** - Proprietary algorithm analyzing military keywords and major power involvement
- **Historical Pattern Analysis** - Tracks escalation patterns over time

### Advanced Features
- **WW3 Doomsday Clock** - Visual threat level indicator (0-100 scale)
- **Admin Command Center** - ML training interface for improving classifications
- **War Room** - Exclusive access area with blockchain-based authentication
- **API Rate Limiting** - Enterprise-grade API management
- **Mobile Responsive** - Full functionality on all devices

## 🏗️ Architecture

### Tech Stack

#### Frontend
- **Framework**: Next.js 14 with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **State Management**: React Query (TanStack Query)
- **UI Components**: Custom components with Lucide icons
- **Performance**: Server-side rendering, optimized caching

#### Backend
- **Framework**: FastAPI (Python 3.11)
- **Database**: MariaDB 10.3 with SQLAlchemy ORM
- **Caching**: Redis with automatic invalidation
- **Migrations**: Alembic for database versioning
- **Task Scheduling**: AsyncIO-based background tasks
- **Authentication**: JWT with bcrypt hashing

#### AI/ML Pipeline
- **Text Analysis**: OpenAI GPT-4o-mini API
- **Alternative**: HuggingFace Transformers support
- **Pattern Learning**: Human-in-the-loop ML feedback system
- **Scoring Algorithm**: Custom threat assessment based on:
  - Military keyword frequency
  - Major power involvement
  - Weapon mentions
  - Nuclear references
  - Geographic proximity

### Data Flow

1. **News Aggregation** → RSS feeds fetched every 3 minutes
2. **Deduplication** → Similar articles grouped (80% similarity threshold)
3. **War Analysis** → Threat scoring based on content
4. **AI Enhancement** → GPT-4 analysis for deeper insights
5. **Caching Layer** → Redis stores processed data
6. **API Delivery** → RESTful endpoints serve frontend
7. **Real-time Updates** → Frontend polls for latest data

## 🚀 Performance

- **Response Time**: <100ms API responses (cached)
- **Update Frequency**: 3-minute news cycles
- **Uptime**: 99.9% availability target
- **Caching**: Multi-layer caching strategy

## 🤝 Contributing

We welcome contributions from developers passionate about global awareness and conflict analysis!

### How to Contribute

1. **Report Issues**: Found a bug or have a suggestion? [Open an issue](https://github.com/yourusername/warcast-public/issues)
2. **Submit PRs**: Have a fix or feature? Submit a pull request to this public repo
3. **Get Access**: Quality contributors will be granted access to the private development repo

### We're Looking For

- 🐍 **Python Developers**: Help improve our AI analysis, API endpoints, and data processing
- 📱 **TypeScript/React Developers**: Enhance the frontend, add visualizations, improve UX

### Contribution Areas

- Improve threat detection algorithms
- Add new data visualizations
- Enhance mobile experience
- Implement new language support
- Optimize performance
- Add new news sources
- Improve AI prompts
- Write documentation

## 👨‍💻 About the Creator

Hi! I'm Robert Schmidt, a developer passionate about leveraging technology to increase global awareness and promote peace through information transparency.

### Connect With Me

- 🐦 **Twitter/X**: [@robb_schmidt](https://x.com/robb_schmidt)
- 🌐 **Website**: [robertschmidt.dev](https://robertschmidt.dev/)

### Support the Project

If you find Warcast.app valuable, consider supporting its development:

- **Ethereum**: `0xaAC0B63a317217675985CC78b7750e6DEfEFf119`
- **Solana**: `robbschmidt.sol`
- **Bitcoin**: `bc1qvg5uvqahyarfcnxmsuds9pvvu56kyekn3hwjf3`

Your support helps maintain the infrastructure, API costs, and continuous development of new features.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

Warcast.app is an information aggregation and analysis platform. All assessments are based on publicly available news sources and AI analysis. This platform should not be used as the sole source for making decisions regarding safety, security, or policy matters. Always consult multiple sources and expert opinions for critical decisions.

---

<div align="center">
  <strong>Stay informed. Stay prepared. Stay peaceful.</strong>
  
  [Visit Warcast.app](https://warcast.app)
</div>

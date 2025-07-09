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

- 📰 **Aggregating news from 50+ trusted sources** including ACLED verified conflict data and GDELT
- 🤖 **AI-powered analysis** using OpenAI (*more models to come) for real-time threat assessment
- 🎯 **Intelligent filtering** with configurable threat thresholds to focus on significant events
- 🗺️ **Entity extraction** identifying countries, organizations, weapons, and key figures
- 📊 **Batch processing** analyzing 20 articles simultaneously for efficiency

## ✨ Key Features

### Real-time Intelligence
- **WebSocket Architecture** - Live data streaming using WebSocket
- **Instant Updates** - Real-time threat level changes and new events
- **Duplicate Detection** - Advanced similarity detection across sources
- **Source Aggregation** - Groups similar stories across multiple sources
- **ACLED & GDELT Integration** - Verified conflict data from academic sources

### AI-Powered Analysis
- **OpenAI GPT Processing** - Advanced threat assessment and entity extraction
- **Rich Entity Extraction** - Identifies:
  - Countries and regions involved
  - Military organizations and groups
  - Key political figures and leaders
  - Weapons systems and military assets
- **Advanced Threat Scoring** - 0-100 scale based on:
  - Military action indicators
  - Nuclear threat detection
  - Cyber warfare mentions
  - Terrorism indicators
- **Key Phrase Extraction** - Captures critical context from each article
- **Local vs Global Classification** - Filters out local incidents to focus on geopolitical events

### Advanced Features
- **Global Threat Indicator** - Visual "doomsday clock" threat level (0-100% scale)
- **WebSocket Channels** - Multiple real-time data streams:
  - News updates channel
  - Threat level changes channel
  - Hourly analysis channel
  - Update history channel
- **Interactive Entity Display** - Color-coded badges for countries, organizations, weapons
- **War Room** - Premium features with Solana wallet authentication:
  - AI Scenario Predictions (48-hour forecasts)
  - Advanced Visualizations (Live conflict maps)
  - Country Risk Profiles
- **Mobile Responsive** - Full functionality on all devices

### Tech Stack

#### Frontend
- **Framework**: Next.js
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **State Management**: React Query (TanStack Query) with WebSocket integration
- **UI Components**: Custom components with Lucide icons
- **Real-time**: WebSocket client with automatic reconnection
- **Performance**: Server-side rendering, optimized caching

#### Backend
- **Framework**: FastAPI
- **Language**: Python
- **Database**: MariaDB with SQLAlchemy ORM
- **Caching**: Redis with automatic invalidation
- **Migrations**: Alembic for database versioning
- **Task Scheduling**: AsyncIO-based background tasks
- **WebSocket Server**: Real-time data broadcasting
- **Authentication**: JWT with secure WebSocket channels

#### AI/ML Pipeline
- **Text Analysis**: OpenAI GPT API for comprehensive analysis
- **War Agent AI**: Autonomous threat prediction using LangChain + Perplexity
- **Unified Processing**: Streamlined pipeline for all data sources
- **Comprehensive Analysis**:
  - Threat score (0-100) with minimum threshold of 20
  - Sentiment analysis (positive/negative/neutral)
  - Entity extraction (countries, orgs, people, weapons)
  - Key phrase identification
  - Threat indicator flags (military, nuclear, cyber, terrorism)
  - Local incident detection to filter non-geopolitical news

### Data Flow

1. **News Aggregation** → RSS feeds from 50+ sources every 3 minutes
2. **External Data** → ACLED conflicts and GDELT events every 6 hours
3. **Pre-filtering** → Excludes non-relevant content (sports, entertainment, etc.)
4. **Deduplication** → Advanced similarity detection across sources
5. **AI Analysis** → OpenAI GPT analyzes threats and extracts entities
6. **Threat Filtering** → Only articles scoring ≥20/100 are saved
7. **WebSocket Broadcasting** → Real-time updates to all connected clients
8. **Caching Layer** → Redis stores processed data with TTL
9. **Frontend Display** → Live updates via WebSocket with rich visualizations

## 🚀 Performance

- **Real-time Updates**: WebSocket delivers updates instantly (no polling)
- **Response Time**: <100ms API responses (cached)
- **Update Frequency**: News every 3 minutes, external data every 6 hours
- **WebSocket Channels**: Separate channels for different data types
- **Database Optimization**: Custom indexes and query optimization
- **Smart Filtering**: Relevance scoring reduces noise by ~90%
- **Caching**: Redis caching with automatic invalidation

## 🤝 Contributing

We welcome contributions from developers passionate about global awareness and conflict analysis!

### How to Contribute

1. **Report Issues**: Found a bug or have a suggestion? [Open an issue](https://github.com/yourusername/warcast-public/issues)
2. **Submit PRs**: Have a fix or feature? Submit a pull request to this public repo
3. **Get Access**: Quality contributors will be granted access to the private development repo - Open a PR here and I'll hook you up!

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

- **Solana**: `robbschmidt.sol`
- **Ethereum**: `0xaAC0B63a317217675985CC78b7750e6DEfEFf119`
- **Bitcoin**: `bc1qvg5uvqahyarfcnxmsuds9pvvu56kyekn3hwjf3`
- **Buy Me a Coffee**: [buymeacoffee.com/robbschmidt](https://buymeacoffee.com/robbschmidt)

Your support helps maintain the infrastructure, API costs, and continuous development of new features.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.l

## ⚠️ Important Disclaimer

**ALL CONTENT IS AI-GENERATED**: Warcast.app uses artificial intelligence to analyze conflicts WITHOUT human intervention or review. Our AI systems can and will make mistakes - just as humans tragically err in conflict situations. 

**POLITICAL NEUTRALITY**: We are completely apolitical and maintain strict neutrality. We do not favor any nation, government, or ideology.

**NOT PROFESSIONAL ADVICE**: This platform provides information only and should not be used as the sole source for decisions regarding safety, security, or policy matters. Always consult multiple sources and expert opinions.

For full disclaimer, privacy policy, and cookie usage, visit: [warcast.app/public-info](https://warcast.app/public-info)

---

<div align="center">
  <strong>Stay informed. Stay prepared. Stay peaceful.</strong>
  
  [Visit Warcast.app](https://warcast.app)
</div>

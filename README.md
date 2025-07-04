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

- 📰 **Aggregating news from 50+ trusted sources** including ACLED verified conflict data
- 🤖 **AI-powered analysis** using OpenAI (*more models to come) for real-time threat assessment
- 🎯 **Intelligent filtering** with configurable threat thresholds to focus on significant events
- 🗺️ **Entity extraction** identifying countries, organizations, weapons, and key figures
- 📊 **Batch processing** analyzing 20 articles simultaneously for efficiency

## ✨ Key Features

### Real-time Intelligence
- **Staging architecture** - Two-stage processing for optimal performance
- **30-second processing cycle** - Rapid analysis of staged articles
- **Duplicate detection** - Advanced hash-based deduplication at multiple levels
- **Source aggregation** - Groups similar stories across multiple sources
- **ACLED integration** - Verified conflict event data from academic sources

### AI-Powered Analysis
- **Batch AI Processing** - GPT-4o-mini analyzes 20 articles in single API call
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
- **Global Threat Indicator** - Visual threat level indicator (0-100% scale)
- **Configurable Threat Filtering** - Minimum score threshold (default: 25/100)
- **Interactive Entity Display** - Color-coded badges for countries, organizations, weapons
- **Detailed AI Analysis Modal** - Shows full assessment with threat indicators
- **Performance Optimizations** - Database indexes, batch operations, pre-filtering
- **Web3 - Solana Wallet Connect** - Access to restricted areas only by wallet login (more blockchain integrations to come)
- **Mobile Responsive** - Full functionality on all devices

## 🏗️ Architecture

### Tech Stack

#### Frontend
- **Framework**: Next.js with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **State Management**: React Query (TanStack Query)
- **UI Components**: Custom components with Lucide icons
- **Performance**: Server-side rendering, optimized caching

#### Backend
- **Framework**: FastAPI
- **Language**: Python
- **Database**: MariaDB 10.3 with SQLAlchemy ORM
- **Caching**: Redis with automatic invalidation
- **Migrations**: Alembic for database versioning
- **Task Scheduling**: AsyncIO-based background tasks
- **Authentication**: JWT with bcrypt hashing

#### AI/ML Pipeline
- **Text Analysis**: OpenAI GPT-4o-mini API exclusively
- **Batch Processing**: Analyzes 20 articles per API call
- **Staging Architecture**: Two-stage pipeline for efficiency:
  1. RSS aggregation → staged_news_items table
  2. AI analysis → news_items table (filtered by threat score)
- **Comprehensive Analysis**:
  - Threat score (0-100) with configurable threshold
  - Sentiment analysis (positive/negative/neutral)
  - Entity extraction (countries, orgs, people, weapons)
  - Key phrase identification (max 5 per article)
  - Threat indicator flags (military, nuclear, cyber, terrorism)
  - Local incident detection to filter non-geopolitical news

### Data Flow

1. **News Aggregation** → RSS feeds fetched into staging table
2. **Pre-filtering** → Excludes non-relevant content (sports, entertainment, etc.)
3. **Deduplication** → Hash-based duplicate detection at staging level
4. **Batch AI Analysis** → GPT-4o-mini processes 20 articles at once
5. **Threat Filtering** → Only articles scoring ≥25/100 are saved
6. **Entity Enrichment** → Extracts and stores structured entity data
7. **Caching Layer** → Redis stores processed data with TTL
8. **API Delivery** → RESTful endpoints with optimized queries
9. **Frontend Display** → Rich visualization with entity badges and detailed modals

## 🚀 Performance

- **Response Time**: <100ms API responses (cached)
- **Processing Speed**: 20 articles analyzed in ~1 seconds
- **Update Frequency**: 30-second staged article processing
- **Database Optimization**: Custom indexes for GUID, content, and processing status
- **Batch Operations**: Bulk inserts and updates for efficiency
- **Smart Filtering**: Pre-filters save ~90% of API calls
- **Caching**: Multi-layer strategy with automatic invalidation

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

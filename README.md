<p align="center">
  <img src="https://warcast.app/warcast-logo.png" alt="Warcast Logo" width="120" />
</p>

<h1 align="center">Warcast.app</h1>
<p align="center"><strong>Real-time Global Conflict Intelligence Platform</strong></p>

<p align="center">
  <a href="https://warcast.app"><img src="https://img.shields.io/badge/Live-warcast.app-red?style=for-the-badge" alt="Live Demo" /></a>
  <a href="https://bags.fm/vT5LomTHPwKJspQnMLczYTmD8z8X5L4rPpBosdXBAGS"><img src="https://img.shields.io/badge/%24WAR-bags.fm-blueviolet?style=for-the-badge" alt="$WAR Token" /></a>
  <a href="https://play.google.com/store/apps"><img src="https://img.shields.io/badge/Android-Play_Store-green?style=for-the-badge&logo=android&logoColor=white" alt="Android" /></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js_14-000000?style=flat-square&logo=next.js&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Python_3.11-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white" alt="Kotlin" />
  <img src="https://img.shields.io/badge/Solana-9945FF?style=flat-square&logo=solana&logoColor=white" alt="Solana" />
  <img src="https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white" alt="OpenAI" />
</p>

---

## About

Warcast monitors global conflicts in real-time by aggregating news from **50+ international sources**, analyzing content with **OpenAI GPT**, **Perplexity**, and **Brave Search**, and delivering critical intelligence through a WebSocket-first interface. The War Agent system provides autonomous threat analysis, 48-hour predictions, multi-agent simulations, and market intelligence — available on web and Android.

<!-- Add a dashboard screenshot: save as docs/screenshots/dashboard.png and uncomment below -->
<!-- <p align="center"><img src="docs/screenshots/dashboard.png" alt="Warcast Dashboard" width="800" /></p> -->

---

## Features

### War Agent Intelligence System

The War Agent is a LangGraph-based orchestration system that autonomously monitors, analyzes, and predicts global conflicts.

- **Perplexity + Brave Search** — Real-time intelligence gathering grounded in current events
- **OpenAI GPT Analysis** — Deep threat assessment, entity extraction, and sentiment scoring
- **Historical Pattern Analyzer** — 90 days of ACLED/GDELT data for escalation pattern detection
- **48-Hour Predictions** — Calculates 24h, 48h, and 1-week escalation probabilities per region
- **Multi-Agent Simulations** — Each major actor (USA, Russia, China, NATO, Iran, etc.) has unique decision profiles modeled on historical behavior
- **Interactive Chat** — WebSocket-based bi-directional chat with persistent history and context-aware responses

<!-- Add a War Agent chat screenshot: save as docs/screenshots/war-agent-chat.png and uncomment below -->
<!-- <p align="center"><img src="docs/screenshots/war-agent-chat.png" alt="War Agent Chat" width="700" /></p> -->

### Real-time Data Pipeline

| Stage | Details |
|-------|---------|
| **Collection** | 50+ RSS feeds (every 3 min), ACLED, GDELT (every 6h), Perplexity, Brave Search |
| **Deduplication** | Hybrid similarity scoring — title (50%), description (20%), keyword overlap (30%) |
| **AI Analysis** | OpenAI GPT batch processing (5 articles at a time), entity extraction, threat scoring |
| **Threat Filter** | Only articles scoring ≥20/100 are persisted; rescoring runs daily for 7-day-old articles |
| **Delivery** | WebSocket v2 pushes updates instantly — no polling, channel-based subscriptions |
| **Caching** | Redis layer with <100ms cached responses and automatic invalidation |

### Smart Alerts V2

Per-user configurable alert system with 10 threat types (escalation, nuclear, cyber, terrorism, economic, humanitarian, military movement, diplomatic, de-escalation, supply chain):

- Severity thresholds (info → critical)
- Region and country filtering
- Source include/exclude lists
- Keyword matching with exclusions
- AI confidence minimum
- Cooldown periods to prevent alert fatigue
- Real-time WebSocket delivery to user-specific channels

### Market Intelligence

GTL (Global Threat Level) correlation analysis against BTC, S&P 500, and Gold with rolling window comparisons. Tracks how geopolitical events move markets.

### Automated X (Twitter) Alerts

Hourly intelligence briefs and critical event alerts posted automatically to [@WarCastApp](https://x.com/WarCastApp).

### Threat Assessment

Scoring system on a 0-100 scale:

| Level | Score | Examples |
|-------|-------|---------|
| **Critical** | 90-100 | Nuclear threats, WMD deployment, world war declarations |
| **High** | 70-89 | Invasions, major offensives, strategic bombings |
| **Elevated** | 50-69 | Military buildups, sanctions, diplomatic breakdowns |
| **Moderate** | 30-49 | Military exercises, border tensions, arms deals |

Multipliers: major power involvement (+15), casualties (+10-20), nuclear keywords (+30).

### Entity Tracking

Extracts and tracks relationships between entities across conflicts — countries, organizations, weapons systems, military units, and key political figures. Relationship types include allied, opposed, controls, supports, and more.

---

## $WAR Token

The **$WAR** token is Warcast's native Solana SPL token powering premium features:

| Feature | Cost |
|---------|------|
| War Agent Chat sessions | $WAR |
| 48-hour predictive forecasts | $WAR |
| Multi-actor simulations | $WAR |
| Premium alert configurations | $WAR |

**Trade $WAR** → [bags.fm/war](https://bags.fm/vT5LomTHPwKJspQnMLczYTmD8z8X5L4rPpBosdXBAGS)

Wallet integration via Solana with Jupiter price feeds. Connect any Solana wallet to get started.

---

## Tech Stack

```
Frontend          Backend            AI/ML               Infrastructure
─────────────     ──────────────     ──────────────────   ──────────────
Next.js 14        FastAPI            OpenAI GPT-4/5       Docker Compose
React 18 + TS     Python 3.11        Perplexity Sonar     Nginx
Tailwind CSS      SQLAlchemy 2.0     Brave Search API     Cloudflare CDN
React Query       MariaDB + Redis    LangChain/LangGraph  GitHub Actions
Privy Auth        Alembic            ACLED + GDELT data   Android (Kotlin)
WebSocket v2      AsyncIO Tasks      Entity extraction     Solana/Jupiter
```

---

## War Room

Premium features accessible via Solana wallet authentication:

**Active:**
- War Agent Chat — Interactive AI conflict analyst
- 48-Hour Predictions — ML-based escalation forecasting
- Multi-Agent Simulations — Actor behavior modeling
- Smart Alerts V2 — Configurable per-user threat notifications
- Market Intelligence — GTL vs market correlation dashboard
- Threat Tracker — Real-time ACLED/GDELT monitoring with AI scoring
- Entity Tracking — Relationship mapping across conflicts

**In Development:**
- War Game — Strategic token-based conflict simulation
- Push Notifications — Mobile and web
- War Council — Community discussion and intel sharing
- Intel Reports — Deep-dive exclusive analysis

---

## Android App

Native Android app built with Kotlin + Jetpack Compose + Material Design 3:

- Real-time WebSocket updates
- Google Sign-In and Solana wallet authentication
- Threat display, news cards, and stats matching the web UI
- Hilt dependency injection

---

## Roadmap (February 2026)

**✅ Completed**
- LangGraph orchestration for autonomous threat analysis
- Perplexity API + Brave Search integration
- War Agent multi-actor simulations with historical patterns
- Enhanced ACLED/GDELT integration with AI scoring
- Smart Alerts V2 with per-user configs, source filtering, cooldowns
- $WAR token launch on Solana
- Market Intelligence dashboard (GTL correlation)
- Automated X (Twitter) intelligence briefs
- Entity tracking and relationship mapping
- Android app with real-time WebSocket updates
- Brave Search news ingestion

**🚧 In Active Development**
- War Game — Strategic token-based conflict simulation
- Push notifications for mobile and web
- Multi-language support
- Enhanced multi-source fact-checking

**🎯 Q2 2026**
- Supply chain disruption modeling
- Economic sanctions impact tracker
- Community-driven intelligence verification
- Android Play Store launch
- Satellite imagery analysis

**🔮 Future**
- Autonomous 7-day predictive modeling
- Defense/security API integrations
- Professional analyst dashboards
- Open-source intelligence (OSINT) network

---

## Contributing

Contributions welcome from developers interested in conflict analysis and AI.

1. **Report Issues** — [Open an issue](https://github.com/robert-schmidt/warcast.app/issues)
2. **Submit PRs** — Submit a pull request to this repo
3. **Get Access** — Quality contributors get access to the private development repo

**Looking for:**
- Python developers — AI analysis, API endpoints, data processing
- TypeScript/React developers — Frontend, visualizations, UX
- Kotlin developers — Android app features and improvements

---

## About the Creator

Built by **Robert Schmidt** — [robertschmidt.dev](https://robertschmidt.dev/)

- **X/Twitter**: [@robb_schmidt](https://x.com/robb_schmidt)
- **Warcast**: [@WarCastApp](https://x.com/WarCastApp)

### Support the Project

| Method | Address |
|--------|---------|
| **Solana (SOL)** | `robbschmidt.sol` |
| **Ethereum (ETH)** | `0xaAC0B63a317217675985CC78b7750e6DEfEFf119` |
| **Bitcoin (BTC)** | `bc1qvg5uvqahyarfcnxmsuds9pvvu56kyekn3hwjf3` |
| **Buy Me a Coffee** | [buymeacoffee.com/robbschmidt](https://buymeacoffee.com/robbschmidt) |

---

## License

MIT License — see [LICENSE](LICENSE) for details.

## Disclaimer

**ALL CONTENT IS AI-GENERATED** without human review. AI systems can and will make mistakes.

**POLITICAL NEUTRALITY**: Warcast is completely apolitical and maintains strict neutrality across all nations and ideologies.

**NOT PROFESSIONAL ADVICE**: Information only — not a substitute for expert security, safety, or policy guidance. Always consult multiple sources.

Full disclaimer: [warcast.app/public-info](https://warcast.app/public-info)

---

<p align="center">
  <strong>Stay informed. Stay prepared. Stay peaceful.</strong><br />
  <a href="https://warcast.app">warcast.app</a>
</p>

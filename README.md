<p align="center">
  <img src="https://warcast.app/warcast-logo.png" alt="Warcast Logo" width="120" />
</p>

<h1 align="center">Warcast.app</h1>
<p align="center"><strong>Real-time Global Conflict Intelligence Platform</strong></p>

<p align="center">
  <a href="https://warcast.app"><img src="https://img.shields.io/badge/Live-warcast.app-red?style=for-the-badge" alt="Live Demo" /></a>
  <a href="https://bags.fm/vT5LomTHPwKJspQnMLczYTmD8z8X5L4rPpBosdXBAGS"><img src="https://img.shields.io/badge/%24WAR-bags.fm-blueviolet?style=for-the-badge" alt="$WAR Token" /></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js_14-000000?style=flat-square&logo=next.js&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Python_3.11-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white" alt="Kotlin" />
  <img src="https://img.shields.io/badge/Solana-9945FF?style=flat-square&logo=solana&logoColor=white" alt="Solana" />
  <img src="https://img.shields.io/badge/Anthropic-191919?style=flat-square&logo=anthropic&logoColor=white" alt="Anthropic" />
  <img src="https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white" alt="OpenAI" />
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white" alt="scikit-learn" />
</p>

---

## About

Warcast monitors global conflicts in real-time by aggregating news from **50+ international sources**, analyzing content with a **unified Brain engine** (Anthropic Claude + RAG + local ML), and delivering critical intelligence through a WebSocket-first interface. The War Agent v2 pipeline provides autonomous hourly intelligence briefs, while a local ML model continuously learns from human analyst corrections.

<!-- Add a dashboard screenshot: save as docs/screenshots/dashboard.png and uncomment below -->
<!-- <p align="center"><img src="docs/screenshots/dashboard.png" alt="Warcast Dashboard" width="800" /></p> -->

---

## Architecture

### Unified Brain Engine

The Brain is the central intelligence layer that provides context-aware analysis across the entire system. It combines **RAG vector search** over live conflict data with **Anthropic Claude** LLMs for scoring, synthesis, and decision-making.

```
                    ┌──────────────────────────────────┐
                    │        Brain (Intelligence)       │
                    │   RAG Vector Index + LLM Router   │
                    └──────────┬───────────────────┬───┘
                               │                   │
                    ┌──────────▼──────┐  ┌────────▼─────────┐
                    │  Anthropic API   │  │   Conflict RAG    │
                    │  Claude Haiku    │  │   Vector search    │
                    │  (bulk scoring)  │  │   over threats,    │
                    │  Claude Sonnet   │  │   articles, memory │
                    │  (deep analysis) │  │                    │
                    └─────────────────┘  └──────────────────┘
```

- **Article Scoring** — Every article is scored with full conflict context (active threats, prior analyses, conflict memory)
- **Hourly Synthesis** — Generates intelligence briefs aware of recent history to avoid repetition
- **Alert Assessment** — Critical events validated by the Brain before social media posting
- **Chat Briefings** — User queries answered with grounding in current conflict data

### Local ML Model (Human-in-the-Loop Learning)

A **GradientBoosting ensemble with 6 specialized classifier heads** runs locally for fast preprocessing and learns incrementally from human analyst corrections:

```
Article → Sentence-BERT Embedding → Feature Extraction → ML Heads
                                                           ├── Threat Score (0-100)
                                                           ├── Novelty Detection
                                                           ├── Escalation Signal
                                                           ├── Entity Extraction (spaCy NER)
                                                           ├── Conflict Sentiment (-1 to +1)
                                                           └── Content Quality Filter
```

- **Incremental Learning** — Admin corrections trigger warm-start retraining (weighted 10x as ground truth)
- **AI-Interpreted Feedback** — Free-text admin reasons are parsed into structured signals (relevance, sentiment, escalation) for richer training
- **Bootstrap from LLM** — Initial training from Anthropic/OpenAI-scored articles, then continuous learning from human feedback
- **Conflict Memory** — Corrections are recorded in a persistent memory graph linked to active threats

### War Agent v2 Pipeline

Autonomous intelligence pipeline running hourly as a dedicated process:

```
 ┌──────────┐    ┌──────────┐    ┌───────────┐    ┌──────────┐
 │ COLLECT   │───▶│ ANALYZE  │───▶│ SYNTHESIZE│───▶│ PUBLISH  │
 │ News,     │    │ ML pre-  │    │ Brain AI  │    │ DB, WS,  │
 │ GDELT,    │    │ scoring, │    │ synthesis │    │ X/Twitter│
 │ Web Search│    │ novelty  │    │ + briefs  │    │ threats  │
 └──────────┘    └──────────┘    └───────────┘    └──────────┘
```

---

## Features

### Real-time Data Pipeline

| Stage | Details |
|-------|---------|
| **Collection** | 50+ RSS feeds (every 3 min), ACLED, GDELT (every 30 min), web search enrichment |
| **Deduplication** | Hybrid similarity scoring — title (50%), description (20%), keyword overlap (30%) |
| **Brain Scoring** | Anthropic Claude with RAG context — every article scored against active conflicts |
| **ML Preprocessing** | Local GradientBoosting ensemble for fast novelty, escalation, and quality filtering |
| **Human Feedback** | Admin corrections weighted 10x, AI-interpreted, fed back into ML model + conflict memory |
| **Delivery** | WebSocket v2 pushes updates instantly — no polling, channel-based subscriptions |
| **Caching** | Redis layer with <100ms cached responses and automatic invalidation |

### Smart Alerts V2

Per-user configurable alert system with 10 threat types (escalation, nuclear, cyber, terrorism, economic, humanitarian, military movement, diplomatic, de-escalation, supply chain):

- Severity thresholds (info to critical)
- Region and country filtering
- Source include/exclude lists
- Keyword matching with exclusions
- AI confidence minimum
- Cooldown periods to prevent alert fatigue
- Real-time WebSocket delivery to user-specific channels

### Automated X (Twitter) Intelligence

Automated posting to [@WarCastApp](https://x.com/WarCastApp):

- **Hourly Briefs** — AI-generated contextual tweets from War Agent analysis (5x daily at fixed UTC hours)
- **Critical Alerts** — Immediate posting for genuine escalation events (ML composite score + Brain validation)
- **Semantic Dedup** — Sentence-BERT embedding similarity (0.80 threshold) prevents repetitive posts
- **Topic Novelty** — Keyword and embedding-based checks reject stale or over-covered topics
- **OG Image Extraction** — Attaches article images to tweets for richer engagement

### Market Intelligence

GTL (Global Threat Level) correlation analysis against BTC, S&P 500, and Gold with rolling window comparisons. Tracks how geopolitical events move markets.

### Threat Assessment

Unified scoring combining Brain (LLM + RAG) and local ML on a 0-100 scale:

| Level | Score | Examples |
|-------|-------|---------|
| **Critical** | 90-100 | Nuclear threats, WMD deployment, world war declarations |
| **High** | 70-89 | Invasions, major offensives, strategic bombings |
| **Elevated** | 50-69 | Military buildups, sanctions, diplomatic breakdowns |
| **Moderate** | 30-49 | Military exercises, border tensions, arms deals |

ML heads provide additional signals: novelty detection, escalation probability, conflict sentiment, and content quality filtering.

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

**Trade $WAR** → [bags.fm](https://bags.fm/vT5LomTHPwKJspQnMLczYTmD8z8X5L4rPpBosdXBAGS)

Wallet integration via Solana with Jupiter price feeds. Connect any Solana wallet to get started.

---

## Tech Stack

```
Frontend          Backend            AI/ML                  Infrastructure
─────────────     ──────────────     ────────────────────   ──────────────
Next.js 14        FastAPI            Anthropic Claude        systemd (prod)
React 18 + TS     Python 3.11        (Haiku + Sonnet)       Docker (dev)
Tailwind CSS      SQLAlchemy 2.0     OpenAI GPT (fallback)  Nginx
React Query       MariaDB + Redis    scikit-learn (local)   Cloudflare CDN
Privy Auth        Alembic            sentence-transformers  GitHub Actions
WebSocket v2      AsyncIO Tasks      spaCy NER              Android (Kotlin)
                                     ACLED + GDELT data     Solana/Jupiter
                                     RAG vector search
```

---

## War Room

Premium features accessible via Solana wallet authentication:

**Active:**
- War Agent Chat — Interactive AI conflict analyst with streaming responses
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

## Android App (In Development)

Native Android app being built with Kotlin + Jetpack Compose + Material Design 3:

- Real-time WebSocket updates
- Google Sign-In and Solana wallet authentication
- Threat display, news cards, and stats matching the web UI
- Hilt dependency injection

---

## Roadmap (March 2026)

**Completed**
- Unified Brain engine (Anthropic Claude + RAG vector search)
- Local ML model with 6 classifier heads and incremental human-in-the-loop learning
- War Agent v2 autonomous intelligence pipeline (hourly)
- Automated X/Twitter posting with semantic dedup and Brain validation
- Enhanced ACLED/GDELT integration with AI scoring
- Smart Alerts V2 with per-user configs, source filtering, cooldowns
- $WAR token launch on Solana
- Market Intelligence dashboard (GTL correlation)
- Entity tracking and relationship mapping
- Web search news enrichment

**In Active Development**
- Android app (Kotlin + Jetpack Compose) with Play Store launch
- War Game — Strategic token-based conflict simulation
- Push notifications for mobile and web
- Multi-language support
- Enhanced multi-source fact-checking

**Q2 2026**
- Supply chain disruption modeling
- Economic sanctions impact tracker
- Community-driven intelligence verification
- Satellite imagery analysis

**Future**
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
- Python developers — AI analysis, ML training pipeline, data processing
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

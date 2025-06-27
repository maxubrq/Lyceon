# Lyceon 📚✨  
*A digital Lyceum for reasoned discourse, live open lectures, and Socratic dialogue.*

![CI](https://img.shields.io/github/actions/workflow/status/your-org/lyceon/ci.yml?style=flat-square)
![License](https://img.shields.io/github/license/your-org/lyceon?style=flat-square)

> **Mission**  
> Re-ignite the spirit of the ancient Lyceum online — a commons where curious minds gather for thoughtful conversation, collaborative learning, and joyful exploration of ideas.

---

## ✨ Core Values
1. **Intellectual Generosity** – share knowledge freely, credit sources, debate in good faith.  
2. **Rigorous Curiosity** – question assumptions, welcome constructive challenge.  
3. **Joyful Learning** – design experiences that feel playful, not pressurized.

---

## 🚀 Feature Highlights (MVP)
| Tier | Feature | Status |
|------|---------|--------|
| **Must** | Account system (OAuth + magic-link) | ☐ |
|        | Schedule & announce lectures | ☐ |
|        | Threaded forum for follow-up | ☐ |
| **Performance** | Low-latency HD streaming | ☐ |
|              | Markdown / LaTeX support | ☐ |
|              | Full-text & semantic search | ☐ |
| **Magic ✨** | AI Socratic Assistant (question prompts) | ☐ |
|             | Live multilingual subtitles & transcripts | ☐ |
|             | Knowledge-graph lecture recaps | ☐ |

---

## 🏗  Tech Stack
| Layer | Tech |
|-------|------|
| **Frontend** | SvelteKit + TypeScript • TailwindCSS |
| **Gateway** | Rust (Actix) WebSockets ⟷ HTTP/GraphQL |
| **Live Video** | RTMP ingest → FFmpeg → Redis Streams |
| **Services** | Rust micro-services, NATS for events |
| **Data** | PostgreSQL (core) • ClickHouse (analytics) |
| **AI** | OpenAI API (GPT-4o) • Whisper • NetworkX |
| **Infra** | Docker • Kubernetes (or Nomad) • Terraform |

---

## 🗺  Quick-Start (Dev)
```bash
# 1. Clone and bootstrap
git clone git@github.com:your-org/lyceon.git
cd lyceon
make init           # installs Rust toolchain, Node, and pre-commit hooks

# 2. Spin up local stack
make dev            # docker-compose: postgres, redis, nats
cargo watch -x run  # backend hot-reload
pnpm dev            # SvelteKit frontend
````

---

## 📐  Architecture Snapshot

```
┌───────────┐  WS  ┌───────────┐
│  Frontend │◄────►│  Gateway  │
└─────┬─────┘      └─────┬─────┘
      │ gRPC/REST        │ NATS
┌─────▼────┐         ┌───▼────────┐
│ Lecture  │         │ Discussion │
│ Service  │         │  Service   │
└─────┬────┘         └────┬───────┘
      │  Redis Stream     │  GraphQL
      ▼                   ▼
   FFmpeg             PostgreSQL
              ▲
              │ events
           ClickHouse
```

---

## 🧪  Tests

```bash
# Rust services
cargo test --all-features

# Frontend
pnpm test
```

---

## 📜  License

[MIT](LICENSE) – because free exchange of ideas should start with free code.

---

## 🤝  Contributing

We welcome pull requests, constructive critiques, and new lecture ideas.
See **CONTRIBUTING.md** for code standards, branch conventions, and our community code of conduct.

---

## 🌟  Get Involved Now

1. **Star** this repo to signal interest.
2. **Open an Issue** proposing a lecture topic or feature.
3. **Join Alpha Cohort** – first 50 sign-ups become founding members with special badges.

> *“Education is the kindling of a flame, not the filling of a vessel.”* — *Plutarch*

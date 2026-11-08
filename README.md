# AFTERMIND AI

> **Personal Autonomous Artificial Intelligence Operating System**

A complete personal AI operating system featuring autonomous agents, visual workflow automation, persistent memory, and continuous background execution.

## ✨ Features

### 🧠 AFTERMIND Brain
- Central reasoning and orchestration engine
- Three execution modes: Direct, Agent, Workflow
- Natural language understanding and task decomposition
- Intelligent agent selection and coordination

### 🤖 Multi-Agent Intelligence
- **Executive**: CEO/Orchestrator, Project Director, Operations Manager
- **Technology**: Software Architect, Senior Engineer, Frontend/Backend, UI/UX, DevOps
- **Business**: Strategist, Market Researcher, Marketing, Sales
- **Intelligence**: Research Analyst, Data Analyst, Innovation Agent
- **Quality**: Security Engineer, QA Engineer, Code Reviewer, Automation Engineer

### 🧠 Advanced Memory Engine
- **Working Memory**: Current conversation context
- **Project Memory**: Technical decisions, files, requirements
- **Long-term Memory**: User preferences, recurring knowledge
- **Episodic Memory**: Previous missions, events, outcomes
- **Semantic Memory**: Searchable knowledge, relationships
- **Document Memory**: Extracted from authorized documents
- Vector embeddings with pgvector for semantic search

### 🎨 Visual Workflow Studio
- React Flow-based node editor
- Drag & drop, zoom, pan, minimap
- 20+ node types: Triggers, AI, Data, Actions, Logic, Human, Utilities
- Real-time execution visualization
- Version history, debugging, checkpoints

### ⚙️ Autonomous Execution Engine
- Persistent task queues with BullMQ/Redis
- Background workers with retry policies
- Scheduled jobs with cron expressions
- Execution checkpoints and recovery
- Idempotency and dead-letter queues

### 🎛️ Command Center (Premium UI)
- Dark luxury design system (Deep black, Electric violet, Midnight navy)
- Responsive PWA with mobile support
- Real-time updates via WebSockets
- 10 main sections: Overview, Chat, Workflows, Agents, Projects, Memory, Automations, Activity, Integrations, Settings

### 🔒 Security & Trust
- Authentication (Credentials, OAuth: GitHub, Google)
- JWT sessions with httpOnly cookies
- Encrypted secret storage
- Rate limiting, CSP, audit logs
- Tool allowlists and permission scopes
- Explicit approval for sensitive operations

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | Next.js 14, React 18, TypeScript, Tailwind CSS |
| **Workflow Editor** | React Flow |
| **State** | Zustand, Jotai, TanStack Query |
| **Backend** | Fastify, Node.js, TypeScript |
| **Database** | PostgreSQL 16 + pgvector |
| **Queue/Cache** | Redis 7, BullMQ |
| **Real-time** | Socket.io |
| **AI** | Anthropic Claude SDK, OpenAI SDK |
| **Auth** | NextAuth.js |
| **Deployment** | Docker Compose, Nginx |

## 🚀 Quick Start

### Prerequisites
- Node.js 20+
- PostgreSQL 16 with pgvector
- Redis 7
- pnpm 9+

### Installation

```bash
# Clone and install
git clone <repo-url>
cd aftermind-ai
pnpm install

# Setup environment
cp .env.example .env
# Edit .env with your configuration

# Setup database
pnpm db:generate
pnpm db:push
pnpm db:seed

# Start development
pnpm dev

# Start background worker (separate terminal)
pnpm worker:dev
```

### Docker Development

```bash
# Start all services
docker-compose up -d

# View logs
docker-compose logs -f app

# Run migrations
docker-compose exec app pnpm db:migrate
```

## 📁 Project Structure

```
aftermind-ai/
├── src/
│   ├── app/                    # Next.js App Router pages
│   │   ├── api/               # API routes
│   │   ├── chat/              # AI Chat interface
│   │   ├── workflows/         # Visual workflow studio
│   │   ├── agents/            # Agent registry & management
│   │   ├── memory/            # Memory browser & search
│   │   ├── projects/          # Project management
│   │   ├── automations/       # Scheduled tasks & triggers
│   │   ├── activity/          # Execution logs & monitoring
│   │   ├── integrations/      # External service connections
│   │   └── settings/          # User & system settings
│   ├── components/
│   │   ├── ui/                # Base UI components
│   │   ├── workflow/          # Workflow editor components
│   │   ├── chat/              # Chat-specific components
│   │   └── providers.tsx      # Context providers
│   ├── lib/
│   │   ├── ai/               # AI service wrappers
│   │   ├── memory/           # Memory engine
│   │   ├── agents/           # Agent registry
│   │   ├── workflows/        # Workflow execution engine
│   │   └── prisma.ts         # Database client
│   ├── runtime/
│   │   └── worker.ts         # Background worker
│   ├── hooks/                # Custom React hooks
│   ├── types/                # TypeScript definitions
│   └── styles/               # Global styles
├── prisma/
│   └── schema.prisma         # Database schema
├── docker/                   # Docker configurations
├── tests/                    # Test suites
└── docs/                     # Documentation
```

## 🔧 Configuration

### Environment Variables

```env
# Database
DATABASE_URL=postgresql://user:pass@localhost:5432/aftermind

# Redis
REDIS_URL=redis://localhost:6379

# Auth
NEXTAUTH_SECRET=your-secret
NEXTAUTH_URL=http://localhost:3000

# AI Models
ANTHROPIC_API_KEY=sk-ant-...
OPENAI_API_KEY=sk-...

# Worker
WORKER_CONCURRENCY=5
WORKER_MAX_RETRIES=3
```

### Key Configuration Files

- `next.config.js` - Next.js with PWA support
- `tailwind.config.ts` - Design system tokens
- `tsconfig.json` - Strict TypeScript config
- `docker-compose.yml` - Full stack deployment
- `prisma/schema.prisma` - Database schema

## 📖 Usage

### AI Chat
Natural conversation with streaming responses, model selection, system prompts, and chat history.

### Workflow Studio
Visual drag-and-drop automation builder with 20+ node types and real-time execution.

### Agent Management
Browse, configure, and execute specialized AI agents for different domains.

### Memory Browser
Search and manage your knowledge base with semantic vector search.

### Projects
Organize work into projects with team collaboration.

## 🧪 Testing

```bash
# Unit tests
pnpm test

# Watch mode
pnpm test:watch

# Coverage
pnpm test:coverage

# E2E tests
pnpm test:e2e
```

## 📦 Deployment

### Production Docker

```bash
# Build images
docker-compose -f docker-compose.yml -f docker-compose.prod.yml build

# Deploy
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

### Environment Checklist
- [ ] Set secure `NEXTAUTH_SECRET` (32+ chars)
- [ ] Configure `ANTHROPIC_API_KEY` and/or `OPENAI_API_KEY`
- [ ] Set up PostgreSQL with pgvector extension
- [ ] Configure Redis with persistence
- [ ] Set up SSL certificates (Let's Encrypt via Certbot)
- [ ] Configure domain DNS
- [ ] Set up monitoring (Sentry, etc.)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests and linting
5. Submit a pull request

## 📄 License

MIT License - see LICENSE file for details.

## 🙏 Acknowledgments

- Anthropic for Claude API
- Vercel for Next.js
- React Flow for workflow visualization
- Prisma for database ORM
- Tailwind CSS for styling
- All open-source contributors

---

Built with ❤️ for personal AI autonomy.

# 🎓 Aprovai — Plataforma de Estudos com IA

> A plataforma de estudos acelerados com IA para ENEM e Concursos Públicos que já aprovou mais de 37.000 estudantes.

![Aprovai Preview](public/og-image.png)

## ✨ Funcionalidades

- 🤖 **IA Tutor Pessoal** — GPT-4 treinado para ENEM e Concursos
- 📚 **Resumos Inteligentes** — IA transforma qualquer conteúdo
- 🃏 **Flashcards Automáticos** — Revisão espaçada com algoritmo SM-2
- 📝 **Simulados Completos** — +120.000 questões comentadas
- 🎯 **Modo Foco** — Ambiente minimalista anti-distração
- 🏆 **Ranking Nacional** — Gamificação com pontos e conquistas
- 📅 **Cronograma Automático** — Plano personalizado por IA
- 📊 **Estatísticas Avançadas** — Dados granulares de desempenho
- 🔥 **Streak Diário** — Sequência de estudos motivacional
- ⏱️ **Pomodoro Integrado** — Timer inteligente de produtividade
- 🎵 **Música Focus** — Lo-fi e binaural beats integrados

## 🛠️ Stack Técnica

| Categoria | Tecnologia |
|-----------|------------|
| Framework | Next.js 15 (App Router) |
| Linguagem | TypeScript |
| Estilização | TailwindCSS + Framer Motion |
| Componentes | Shadcn/ui + Radix UI |
| Auth | Clerk |
| Banco de dados | PostgreSQL + Prisma ORM |
| IA | OpenAI GPT-4o-mini |
| Pagamentos | Stripe + Mercado Pago |
| Upload | Cloudinary |
| Deploy | Vercel |

## 🚀 Como rodar localmente

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/aprovai.git
cd aprovai
```

### 2. Instale as dependências

```bash
npm install
```

### 3. Configure as variáveis de ambiente

```bash
cp .env.example .env.local
```

Preencha todas as variáveis no `.env.local`:

- **DATABASE_URL** — PostgreSQL (recomendo [Neon](https://neon.tech) grátis)
- **CLERK_***: Crie em [clerk.com](https://clerk.com)
- **STRIPE_***: Crie em [stripe.com](https://stripe.com)
- **OPENAI_API_KEY**: Crie em [platform.openai.com](https://platform.openai.com)
- **CLOUDINARY_***: Crie em [cloudinary.com](https://cloudinary.com)

### 4. Configure o banco de dados

```bash
npm run db:push    # Aplica o schema
npm run db:generate  # Gera o Prisma Client
npm run db:seed   # Popula com dados iniciais (opcional)
```

### 5. Rode o projeto

```bash
npm run dev
```

Acesse [http://localhost:3000](http://localhost:3000)

## 📁 Estrutura de Pastas

```
aprovai/
├── prisma/
│   └── schema.prisma          # Schema completo do banco
├── src/
│   ├── app/
│   │   ├── layout.tsx          # Root layout (Clerk + fonts)
│   │   ├── page.tsx            # Landing page
│   │   ├── dashboard/          # Área logada
│   │   │   ├── layout.tsx
│   │   │   ├── page.tsx
│   │   │   ├── simulados/
│   │   │   ├── flashcards/
│   │   │   ├── resumos/
│   │   │   ├── ia-tutor/
│   │   │   ├── ranking/
│   │   │   ├── cronograma/
│   │   │   └── estatisticas/
│   │   └── api/
│   │       ├── ai/chat/        # IA Tutor (streaming)
│   │       ├── subscriptions/  # Checkout Stripe
│   │       └── webhooks/
│   │           ├── stripe/
│   │           └── clerk/
│   ├── components/
│   │   ├── landing/            # Componentes da landing
│   │   │   ├── Navbar.tsx
│   │   │   ├── Hero.tsx
│   │   │   ├── SocialProof.tsx
│   │   │   ├── Features.tsx
│   │   │   ├── DashboardPreview.tsx
│   │   │   ├── Testimonials.tsx
│   │   │   ├── Pricing.tsx
│   │   │   ├── FAQ.tsx
│   │   │   ├── CTA.tsx
│   │   │   ├── Footer.tsx
│   │   │   └── LiveActivity.tsx
│   │   └── dashboard/
│   │       ├── Sidebar.tsx
│   │       └── Topbar.tsx
│   ├── lib/
│   │   ├── prisma.ts           # Prisma client singleton
│   │   └── stripe.ts           # Stripe utilities
│   ├── types/
│   │   └── index.ts            # TypeScript types
│   ├── middleware.ts            # Clerk auth middleware
│   └── styles/
│       └── globals.css         # Design system CSS
└── .env.example                # Variáveis necessárias
```

## 💳 Planos e Preços

| Plano | Preço | Período |
|-------|-------|---------|
| Mensal | R$ 29,90 | /mês |
| Semestral | R$ 19,90 | /mês (cobrado R$ 119,40) |
| Vitalício | R$ 297 | único |

## 🔒 Autenticação

Usando [Clerk](https://clerk.com) com:
- Login com email/senha
- Login social (Google, GitHub)
- Webhooks para sincronizar com banco
- Middleware de proteção de rotas

## 🌐 Deploy na Vercel

```bash
# Instale a Vercel CLI
npm i -g vercel

# Deploy
vercel

# Configure as variáveis de ambiente no dashboard da Vercel
```

### Variáveis obrigatórias na Vercel:
Todas as variáveis do `.env.example` devem ser configuradas no painel da Vercel em **Settings → Environment Variables**.

## 🔧 Scripts disponíveis

```bash
npm run dev          # Desenvolvimento
npm run build        # Build de produção
npm run start        # Iniciar em produção
npm run lint         # Lint
npm run db:push      # Atualizar banco
npm run db:generate  # Gerar Prisma Client
npm run db:studio    # Prisma Studio (GUI)
npm run db:seed      # Popular banco com dados iniciais
```

## 📈 Roadmap

- [ ] App mobile (React Native / Expo)
- [ ] Modo offline para flashcards
- [ ] Integração com edital de concursos
- [ ] Grupos de estudo
- [ ] Videoaulas integradas
- [ ] Correção automática de redação

## 📄 Licença

MIT — Sinta-se livre para usar, modificar e distribuir.

---

Feito com 💜 para estudantes brasileiros que querem conquistar a aprovação.

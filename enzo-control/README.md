# ENZO CONTROL

Painel de controle operacional e comercial da **Enzo Auto Service**.

SaaS interno para dar visibilidade total da operação da oficina: captação de
leads, agendamentos, Kanban operacional em tempo real, apontamento de horas
dos mecânicos via tablet-na-baia, telas de TV para salão e gestão, e
dashboards financeiros e de KPIs consumindo dados do **Mitchell1** (sistema
atual de gestão da oficina).

> Status: **planejamento**. Ainda não há código — apenas documentação.
> Toda a estrutura, decisões e roadmap estão em [`docs/PLANEJAMENTO.md`](docs/PLANEJAMENTO.md).

## Stack alvo

- **Next.js 15** (App Router) + TypeScript
- **Supabase** (Postgres + Auth + Storage + Realtime)
- **Tailwind CSS** + **shadcn/ui**
- **dnd-kit** (Kanban)
- **Recharts** / **Tremor** (dashboards)
- **Vercel** (deploy contínuo via GitHub)

## Estrutura desta pasta

```
enzo-control/
├── README.md                    # este arquivo
├── docs/
│   └── PLANEJAMENTO.md          # plano completo: arquitetura, módulos, roadmap
├── supabase/
│   └── schema.sql               # SQL inicial para criar o banco no Supabase
└── assets/
    ├── README.md                # instruções para colocar o logo aqui
    └── logo-enzo-auto-service.png  # (a ser adicionado pelo time)
```

## Próximos passos

1. Revisar [`docs/PLANEJAMENTO.md`](docs/PLANEJAMENTO.md) e validar decisões
2. Criar projeto no Supabase e rodar [`supabase/schema.sql`](supabase/schema.sql)
3. Adicionar o logo em `assets/logo-enzo-auto-service.png`
4. Confirmar retorno do Mitchell1 sobre integração (API / DB / CSV)
5. Iniciar Sprint 0 (fundação Next.js + Supabase Auth + tema Enzo)

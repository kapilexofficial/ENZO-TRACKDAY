# ENZO EXPERIENCE — Project Manager

Aplicativo web de gerenciamento do evento **ENZO EXPERIENCE — Track & Friends** no Sebring International Raceway.

**Ao vivo:** https://enzo.thesecretx.com

## O que é

Ferramenta de gestão de projeto feita sob medida pra acompanhar o planejamento do evento:

- **Dashboard** — métricas, progresso por área, prazos, atividade recente
- **Kanban** — colunas arrastáveis (Backlog → A Fazer → Em Andamento → Em Análise → Concluído)
- **Lista** — tabela com ordenação e filtros
- **Atividade** — feed cronológico de tudo que foi alterado (quem, o quê, quando)
- **Planejamento** — documento executivo completo do evento

Cada tarefa tem título, descrição, responsável, prazo, prioridade, checklist e histórico completo de alterações.

## Stack

- **Frontend:** HTML + CSS + JavaScript puro (sem build, sem framework)
- **Backend:** Supabase (Postgres + PostgREST)
- **Hospedagem:** Vercel (estático)
- **Domínio:** `enzo.thesecretx.com` (DNS via Cloudflare)

Arquitetura:

```
Browser → enzo.thesecretx.com (Vercel CDN)
            ↓ fetch REST + anon key
          Supabase (Postgres)
```

Sem backend próprio: o frontend chama direto o PostgREST do Supabase, RLS com policy permissiva (ferramenta interna privada).

## Estrutura

```
app/
├── index.html          # toda a aplicação (UI + lógica + estilos)
├── vercel.json         # config do deploy
├── data/
│   ├── logo_enzo_track.png   # logo principal
│   └── logo.svg              # fallback svg
└── README.md
```

## Deploy

Deploy automático via Vercel — todo `git push` pra `main` dispara um novo deploy.

Para deploy manual:

```bash
cd app
vercel --prod
```

## Desenvolvimento local

É só abrir o `index.html` num servidor estático:

```bash
cd app
python3 -m http.server 8080
```

E acessar http://localhost:8080 — vai conectar no mesmo Supabase de produção.

## Dados

Todas as tarefas, histórico e configurações ficam no Supabase:

- Projeto: `enzo-trackday`
- Tabelas: `tasks`, `config`

Nada fica salvo no cliente — tudo sincroniza entre dispositivos.

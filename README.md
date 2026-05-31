# AI Inventory Management SaaS

> Upload a CSV. Know exactly what to order, when, and how much.

## What it does

A SaaS platform for small and mid-size businesses with physical inventory.

The owner uploads a CSV with product data. The system automatically:

- **Predicts** when each item will run out based on sales velocity
- **Flags critical stock** — items running out in under 10 days
- **Generates AI recommendations** (LLaMA 3.1 via Groq) — exact reorder quantities
- **Calculates financial KPIs** — total warehouse value, revenue forecast, capital frozen in dead stock
- **Generates a Purchase Order** for the supplier in one click

Target: small and mid-size B2B businesses managing physical inventory.

---

## Tech Stack

**Frontend**  
![Next.js](https://img.shields.io/badge/Next.js_14-000000?style=flat&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![React](https://img.shields.io/badge/React_18-61DAFB?style=flat&logo=react&logoColor=black)
![Recharts](https://img.shields.io/badge/Recharts-22B5BF?style=flat&logoColor=white)

**Backend**  
![Next.js](https://img.shields.io/badge/API_Routes-000000?style=flat&logo=next.js&logoColor=white)
![Groq](https://img.shields.io/badge/Groq_SDK-F55036?style=flat&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat&logo=supabase&logoColor=white)

**Infrastructure**  
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)

---

## Architecture decisions

| Decision | Reason |
|----------|--------|
| Next.js API Routes | Serverless — no separate backend to maintain solo |
| Groq + LLaMA 3.1 8B | Fast inference, cost-efficient for per-request AI calls |
| Supabase | PostgreSQL + Auth + RLS in one — right for a solo build |
| CSV input | Zero onboarding friction — works with any existing workflow |
| Vercel | Zero-config CI/CD, native Next.js support |

---

## Security

- Route protection via Next.js Middleware
- Auth guard on all API endpoints
- Row Level Security (RLS) on all database tables
- No secrets in repository — all env vars via Vercel

---

## Internationalization

4 languages: `EN` `RU` `ZH` `TR`  
Custom i18n provider on React Context. Automatic browser language detection.

---

## Status

`Pre-launch` — payment integration in progress.  
Core product is complete and deployed.

---

*Built solo. Full stack. Every decision made by one person.*

# Shiryu Studios LLC
Shiryu Studios is a boutique product and cloud services studio building purposeful, people-first digital experiences for Shiryu Studios’ own suite of sites and tooling.

## What we build
- **Shiryu.Main:** the public marketing homepage, careers site, and Shiryu Help experience that introduces visitors to our services.
- **Shiryu.Cloud:** the client dashboard and automation workspace for customers managing Shiryu-hosted sites, billing, and help articles.
- **Shiryu.Team:** the internal operations portal for scheduling, recruiting, finance, help tickets, and team-wide tooling.
- **Shiryu.Auth, Shiryu.Mail:** lightweight front-ends that surface OAuth/login flows and mail webhooks while offloading stateful logic to the centralized Shiryu.Api worker.
- **Shiryu.Api:** the canonical edge API worker. Every `/api/*` route inside the product family lives here so we can deploy shared business logic, data access, and guardrails once and call it from every other app.

## How we work
- We prefer Cloudflare Pages + Workers for fast, global deployment with D1/R2 bindings for data and storage.
- Each app targets Node 20+ / npm 10+, Vite 7 + React 19, and simple tests via Vitest whenever a suite exists.
- All `/api/*` requests go through `https://api.shiryustudios.com`, so the front-end repos focus on UI and assets while the API worker owns the backend.
- Shared helpers (auth, API clients, help articles, etc.) live in `src/lib` or `functions/_shared` where relevant so everything is consistent.

## Community / contributions
- We’re building for ourselves, so contributions happen via internal requests. Open-source folks can follow the repos for state updates, but all actual work lives inside the Shiryu Studios GitHub org.
- Need to deploy a change? Update the corresponding repo, run its `npm run build`/`test` scripts, and push—Cloudflare Pages/Workers pick it up automatically when the project is wired to GitHub.

## Learn more
- Visit `https://www.shiryustudios.com` for the full customer story.
- Each repo includes its own README with stack, deployment, and testing details; start with the repo table of contents on the main branch to explore.

# OSIMAP: Accident Mapping & Analytics

A full‑stack platform for visualizing and analyzing traffic accident data. It combines an authenticated, map‑first UI with background analytics and exportable insights for reporting and decision support.

Thesis project — Team of 6 (Pampanga State University)

## My Role

I contributed to the React frontend as part of a team effort, working on the map interface, data visualization, and dashboard components.

## What it does
- Map exploration with heatmaps, marker clustering, filters, and print‑ready views.
- Secure, role‑based access with session management and protected routes.
- File uploads with background cleaning and HDBSCAN clustering.
- Dashboards, profiles, admin tools, and a separate download portal.

## Architecture at a glance
- Frontend: React (CRA), React Router, React Leaflet, Chart.js, Lucide.
- Services:
  - Root Node/Express: support email + healthcheck.
  - Backend Node/Express: upload orchestration and processing.
  - Python pipeline: cleaning, clustering (HDBSCAN), GeoJSON export.
- Data: Supabase JS client for auth/storage.
- Additional: Next.js download page (sub‑app: `osimap-download-page/`).

Monorepo layout:
- `src/` React app (protected routes, contexts, map, dashboards)
- `server.js` Root Express service (support email, health)
- `backend/` Node service + Python scripts (analytics pipeline)
- `osimap-download-page/` Next.js download portal

## Tech highlights
- React 19, React Router 7 with Suspense code‑splitting.
- Leaflet ecosystem: heat, fullscreen, marker clusters.
- Supabase integration for auth and data access.
- Python HDBSCAN for robust density‑based clustering.

## Status

Undergraduate thesis project. Not currently deployed.

## Quickstart (dev)
- Requirements: Node 18+, npm, Python 3.10+
- Env (examples):
  - `EMAIL_USER`, `EMAIL_PASS` (SMTP/Gmail for support)
  - `REACT_APP_SUPABASE_URL`, `REACT_APP_SUPABASE_ANON_KEY`
- Install: `npm install`
- Run all services: `npm run dev`

## Demo targets
- Auth‑gated dashboard and interactive map with advanced filters.
- Upload flow with progress and background processing.
- Printable reports and admin functionality.
- Download page for sharing curated datasets/artifacts.
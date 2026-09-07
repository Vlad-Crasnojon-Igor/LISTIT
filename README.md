# LISTIT

A full-stack marketplace platform for social-media-based sellers in Moldova.

I built this as a two-person team from an MVP specification,product-engineering project — problem definition, data model, API design, frontend, async processing, and deployment in one coherent codebase.

## The problem

Small businesses in Moldova sell almost exclusively through Instagram, TikTok and Facebook. They get reach, but no real storefront, no structured catalog, and no trust signal for buyers outside their followers. LISTIT sits between buyer and seller for verified businesses only: a real, store-first marketplace with catalog stock, order dashboards and commission accounting — the gap the dominant classifieds site doesn't fill.

## What I built

- **Storefronts** — each verified business gets a public store page (logo, banner, catalog, ratings), with product variants (size/color), stock quantities and auto-hide when out of stock.
- **Global search & catalog** — cross-store product search with category and price filters via django-filter.
- **Buyer flow** — browsing without an account, lightweight purchase accounts, order status tracking (paid → confirmed → shipped → delivered), ratings and reviews.
- **Seller tools** — order management dashboard, payout dashboard with per-order commission calculation and history.
- **Admin console** — business verification before a store goes live, subscription billing enforcement, commission ledger reconciliation.

## Engineering

- **Backend:** Django 6 + Django REST Framework, SimpleJWT auth, drf-spectacular (OpenAPI schema), drf-nested-routers, django-filter, structlog, django-csp.
- **Async:** Celery + Redis for background jobs (image processing, notify work).
- **Images:** S3-compatible media storage (boto3 + django-storages) with Pillow auto-thumbnailing on upload.
- **Frontend:** React 19 + TypeScript + Vite + Tailwind CSS 4, react-router, Sentry on both sides.
- **Hardening:** CSP headers, CORS configured, error tracking via Sentry (django-sdk + react-sdk), structlog structured logging.
- **Testing:** pytest suites for the API (catalog endpoints, permissions, image handling) plus Vitest + React Testing Library on the frontend.
- **Deployment:** Docker Compose across services, Gunicorn, seeded PostgreSQL.

## Snapshot

- ~90 commits over a focused sprint (July 27 – August 3, 2026), PR-based flow.
- MVP scope from the spec — buyer flow, seller flow and admin console — implemented, tested and containerized.

Source available on request.

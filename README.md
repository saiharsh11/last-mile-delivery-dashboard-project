# Dubai Last-Mile Delivery Analytics Dashboard

A data analytics dashboard simulating last-mile delivery operations across 15 Dubai zones over 6 months — 133,000+ (Synthetic Data NOT REAL!) orders, 50 drivers (Synthetic Data NOT REAL!), built to surface real operational insights through SQL and data visualization.

## What it shows

- **KPI Cards** — Total orders, avg delivery time, on-time rate, active drivers, avg distance, avg delay
- **Peak Hour Analysis** — Order volume vs. avg delay by hour (identifies 12–14h lunch peak and 18–21h evening peak)
- **Zone Performance** — Avg delay ranked by Dubai zone (Downtown, Deira, Marina, Al Quoz, etc.)
- **Delay Root Cause** — Peak vs off-peak comparison with traffic score correlation
- **Daily Trends** — 6-month order volume and on-time rate over time
- **Category Breakdown** — Orders by product category (Grocery, Electronics, Fashion, etc.)
- **Driver Productivity** — Sortable table of 50 drivers with deliveries, on-time %, delay, distance
- **Inline SQL Viewer** — Every chart shows the exact SQL query behind it

## Tech Stack

| Layer | Tech |
|---|---|
| Frontend | Next.js 14 (App Router), Recharts, Tailwind CSS |
| Data | Python, SQLite, standard library only |
| Deployment | Vercel |

## Data Pipeline

```
generate_data.py  →  delivery.db  →  analyze.py  →  public/data/*.json  →  Next.js (build time)
```

Synthetic data generated with Python — 15 real Dubai zones with coordinates, realistic peak-hour traffic simulation, and delay modeling based on zone congestion, batch size, and distance. The Next.js server component reads pre-generated JSON files at build time — no API routes or runtime database needed.

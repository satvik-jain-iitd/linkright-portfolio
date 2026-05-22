# Portfolio + Career Dashboard — Powered by LinkRight

This repository hosts a public portfolio site and auto-generated career dashboard published via [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills).

## Live pages

| Page | URL | What it shows |
|---|---|---|
| Portfolio | `https://<username>.github.io/linkright-portfolio/` | About, work samples, featured projects |
| Case Studies | `https://<username>.github.io/linkright-portfolio/cases/` | Deep-dive project writeups |
| Career Dashboard | `https://<username>.github.io/linkright-portfolio/dashboard/` | Live Kanban of your job pipeline |

## Structure

```
/
├── index.html             ← portfolio homepage
├── cases/                 ← case study pages
└── dashboard/
    └── index.html         ← auto-generated from pipeline.json (no server needed)
```

## Dashboard

The career dashboard is a static HTML file auto-generated from your `pipeline.json` by `/linkright-push`. It shows all tracked opportunities by stage (saved → applied → screening → interview → offer). No login. No database. Updates every time you push.

## Managed by

[`/linkright-push`](https://github.com/satvik-jain-iitd/linkright-skills) — do not edit the dashboard manually. Portfolio content can be edited directly.

---

*Part of the [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills) AI career OS.*

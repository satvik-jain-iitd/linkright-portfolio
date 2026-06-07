# Portfolio and Career Dashboard, by LinkRight

This repo hosts my public portfolio site and a live career dashboard, both generated and published by [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills), the career OS I built.

The portfolio turns my real work into case studies and project writeups. The dashboard is a static, login-free Kanban of my job pipeline, regenerated on every push. No server, no database, just files served by GitHub Pages.

## Live pages

| Page | URL | What it shows |
|---|---|---|
| Portfolio | `https://<username>.github.io/linkright-portfolio/` | About, work samples, featured projects |
| Case studies | `https://<username>.github.io/linkright-portfolio/cases/` | Deep-dive project writeups |
| Career dashboard | `https://<username>.github.io/linkright-portfolio/dashboard/` | Live view of the job pipeline by stage |

## Structure

```
/
  index.html              # portfolio homepage
  cases/                  # case study pages
  dashboard/
    index.html            # generated from pipeline.json, no server needed
```

## The dashboard

The dashboard is one static HTML file, generated from `pipeline.json` by `/linkright-push`. It lays out every tracked opportunity by stage: saved, applied, screening, interview, offer. No login, no database. It updates every time I push.

## Managed by the system

Do not edit the dashboard by hand; `/linkright-push` owns it. Portfolio content can be edited directly.

Part of [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills), a local-first career OS.

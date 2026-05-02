<div align="center">

# 🏛️ CapWatch Public

**OSINT tracker for US Capitol surveillance systems and contractor spending**

[![Cloudflare Workers](https://img.shields.io/badge/Cloudflare_Workers-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)](https://workers.cloudflare.com)
[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL_3.0-blue?style=for-the-badge)](LICENSE)
[![VPDLNY](https://img.shields.io/badge/VPDLNY-Mission_Tool-8B0000?style=for-the-badge)](https://osintnet.uk)

</div>

---

## What Is This

CapWatch tracks surveillance technology procurement at the US Capitol — cameras, biometrics, access control systems, and the contractors who supply them.

Built on public contract data from USASpending.gov and FOIA disclosures. Everything here is public record.

---

## Data Sources

- **USASpending.gov** — Federal contract awards
- **QuiverQuant** — Congressional contract tracking
- **FOIA disclosures** — MuckRock database
- **GAO reports** — Government accountability findings

---

## Architecture

```
Cloudflare Worker (capwatch-public)
     │
     ├── D1 (contract records, vendor database)
     ├── KV (news cache, rate limiting)
     └── REST API (/api/contracts, /api/vendors, /api/news)
```

---

## Self-Hosting

```bash
git clone https://github.com/indicaindependent/capwatch-public
cd capwatch-public
cp wrangler.toml.example wrangler.toml

wrangler d1 create capwatch-db
wrangler secret put QUIVERQUANT_API_KEY
wrangler secret put NEWS_API_KEY
wrangler deploy
```

---

## License

[AGPL-3.0](LICENSE) — Modifications must be open-sourced.

---

<div align="center">
<sub>Public record data only | Built by <a href="https://osintnet.uk">VPDLNY</a></sub>
</div>

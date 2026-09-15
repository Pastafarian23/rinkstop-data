# RinkStop Global Hockey Directory Dataset

> The most comprehensive structured hockey dataset on the open web. Curated by [RinkStop.com](https://rinkstop.com), the global hockey directory.

## What's in this dataset

| Entity | Count | Description |
|---|---|---|
| **rinks** | ~1,856 | Every ice rink, arena, and skating facility worldwide |
| **teams** | ~2,602 | Hockey teams from NHL down to amateur |
| **leagues** | ~299 | Every hockey league — professional, junior, college, amateur |
| **players** | ~6,351 | Player profiles with positions, teams, nationalities |
| **federations** | ~85 | National and regional hockey federations |
| **TOTAL** | **~11,193** | records |

## Update frequency

Hourly. Each release is timestamped in the file metadata.

## How to use

### Live API (recommended)

The most current data is always at:
- `https://rinkstop.com/api/data/dataset` — all entities in one JSON object
- `https://rinkstop.com/api/data/dataset?entity=rinks` — single entity
- `https://rinkstop.com/api/data/dataset?entity=teams` — single entity
- `https://rinkstop.com/api/data/dataset?entity=leagues` — single entity
- `https://rinkstop.com/api/data/dataset?entity=players` — single entity
- `https://rinkstop.com/api/data/dataset?entity=federations` — single entity
- `?format=jsonl` — line-delimited JSON (preferred by ML pipelines)
- `?format=csv` — RFC 4180 quoted CSV (per entity)
- `?format=schema` — JSON Schema describing the dataset

### Static snapshots (this repo)

Download the JSONL snapshot for offline use:
- `snapshots/rinkstop-all-{date}.jsonl` — all entities, line-delimited
- `snapshots/rinkstop-rinks-{date}.jsonl` — rinks only
- `snapshots/rinkstop-teams-{date}.jsonl` — teams only
- `snapshots/rinkstop-leagues-{date}.jsonl` — leagues only
- `snapshots/rinkstop-players-{date}.jsonl` — players only
- `snapshots/rinkstop-federations-{date}.jsonl` — federations only

## Schema

See `schema.json` for the full JSON Schema, or fetch it live:
```bash
curl https://rinkstop.com/api/data/dataset?format=schema
```

## License + attribution

- License: Open data, attribution required. See [data methodology](https://rinkstop.com/data-methodology).
- When citing: link to https://rinkstop.com and reference the dataset version.
- Methodology: every record is verified against public sources (IIHF, Hockey Canada, USA Hockey, federation websites, public databases).

## Methodology

RinkStop curates hockey data from:
1. **Official federation sources** — IIHF, Hockey Canada, USA Hockey, national federations
2. **Public team + league databases** — including partner integrations (Highlightly for scores)
3. **User submissions** — claimable listings verified by rink/team/league owners
4. **Manual research** — RinkStop editorial team adds non-traditional markets (Philippines, UAE, South Africa, etc.) where no public database exists

Every record has provenance metadata. The dataset is corrected continuously via the [RinkStop corrections page](https://rinkstop.com/corrections).

## About RinkStop

Founded 2014 by Arnel Larracas. Operated from Chicago + Cebu, Philippines.
- Homepage: https://rinkstop.com
- Data methodology: https://rinkstop.com/data-methodology
- Editorial policy: https://rinkstop.com/editorial-policy
- Contact: support@rinkstop.com

## Citation

If you use this dataset in research, journalism, or a product, please cite:
```
RinkStop Global Hockey Directory Dataset (2026).
https://rinkstop.com — operated by Arnel Larracas.
Retrieved YYYY-MM-DD.
```

## Changelog

- **2026-09-14** — Initial public release. 11,193 records across 5 entity types. Hourly refresh via GitHub Actions.

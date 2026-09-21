# fastQuote Community Rates & Templates

Community-maintained reference rates for fabricators, machine shops,
and construction estimators — **generic rate data only**: materials
$/lb by alloy, labor $/hr by trade, machine $/hr by process, and
installed-assembly costs per uom.

**This repo never contains part-number-level prices, customer data,
or the fastQuote engine.** The engine is closed-source and separately
licensed at [fastquote.app](https://fastquote.app).

## Licenses

| Content | License |
|:---|:---|
| Rate data (`rates/*.csv`) and template workbooks (`templates/`) | **CC BY 4.0** — see `LICENSE-DATA.md`. Use commercially with attribution. |
| Code (validator, repo plumbing) | **Apache-2.0** — see `LICENSE`. |

## The data

| File | Contents |
|:---|:---|
| `rates/materials.csv` | $/lb by alloy (A36, 304SS, 6061…), $/ft structural shapes, $/sqft sheet/plate |
| `rates/labor.csv` | $/hr by trade (welder, machinist, electrician, pipefitter…) |
| `rates/machines.csv` | $/hr or $/lb by process (laser cutting, press brake, CNC, FDM printing…) |
| `rates/assemblies.csv` | Installed cost per uom (roofing $/sqft, concrete $/yd³, painting $/sqft…) |

Schema (one flat row per rate):

```csv
category,item,uom,rate,currency,region,effective_date,source,source_url,notes
material,A36,LB,4.80,USD,US,2026-09-20,vendor-quote,https://example.com,mild structural steel
```

## Contributing

Every rate row must carry an `effective_date` and a `source` — an
unsourced number is not a rate. PRs are validated automatically by
`validator.py` (stdlib-only; see `CONTRIBUTING.md` for the rules and
data boundaries).

The reward flywheel: **20 sourced rate rows → 3 months of fastQuote
free.** Submit via GitHub PR here, or through the Discord bot in
`#rate-submissions` (non-devs never touch git).

## Community

- [Discord](https://discord.gg/fastquote) — office hours, rate discussions
- [YouTube](https://youtube.com/@fastquote) — estimating walkthroughs

Rates are community-contributed reference data with no warranty —
**every shop must validate rates against its own costs before
quoting.**

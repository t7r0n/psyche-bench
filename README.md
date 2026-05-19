# Psyche Bench

The clinical ML evaluation harness Mindset needs before any "foundation model of psychophysiology" can ship safely across Nerva, Evia, Claria, Relio and Finito - a versioned offline eval framework plus a per session telemetry schema that produces IBS SSS equivalent outcome predictions from the first 7 days of app behavior.

## Why This Exists

Mindset's pitch evolution - "hypnotherapy apps" -> "foundation model of psychophysiology" - has out run its public engineering. The clinically published Nerva RCT (PMC11179457) reports adherence and persistence as the primary moderator of outcome, not session content. Yet a user opening Nerva today gets the same 42 day program regardless of whether they are a 28 year old IBS D patient who skips session 7 because of nausea, a 55 year old IBS C patient with high anxiety baseline, or a relapser on attempt 3.

## What It Builds

- Replays synthetic `mindset` and `pitch` cases against the project's evidence rules.
- Scores `mindset_coverage`, `pitch_risk`, and `evolution_precision` so regressions are visible in CSV and JSON.
- Plants `mindset drift` and `pitch gap` failures as negative controls.
- Writes citation-locked decision claims; unsupported claims fail verification.
- Exports a review dashboard and demo pack for `psyche-bench` without hosted services.

## Local Run

```bash
uv sync
uv run psyche-bench all
uv run pytest -q
uv run ruff check .
```

## Outputs

- `outputs/analysis.json`
- `outputs/scenario_report.csv`
- `outputs/decision_report.md`
- `outputs/evidence_packet.md`
- `outputs/dashboard.html`
- `outputs/demo_pack.zip`

## Sources

- https://mindsethealthlabs.com/
- https://pmc.ncbi.nlm.nih.gov/articles/PMC11179457/
- https://www.monash.edu/medicine/news/latest/2024-articles/hypnotherapy-reduces-irritable-bowel-syndrome-symptoms-and-now-theres-an-app-for-that
- https://onlinelibrary.wiley.com/doi/10.1111/nmo.14533
- https://www.mindsethealth.com/mindset-health-series-a-afr
- https://balancethegrind.co/interviews/alex-naoumidis-co-founder-co-ceo-at-mindset-health/
- https://www.prnewswire.com/news-releases/mindset-health-raises-us12m-to-expand-digital-hypnotherapy-apps--scale-distribution-301776991.html
- https://www.ycombinator.com/companies/mindset-health

## Boundary

This repository uses synthetic fixtures only. It has no credentials, no customer data, no outreach data, and no dependency on a hosted API.

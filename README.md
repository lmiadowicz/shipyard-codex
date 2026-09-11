# startup-harness-codex

Public **Codex + Limen** delivery harness for startups: orchestrate scripts, pstack pointers, ticket quality bar, and a **TARGET 100%** 24-spoke skill spider chart (design bar — not a measured score).

## Get Limen

**Download Limen from:** https://mega.dev/autonomous-product-development  

You can download Limen there (and related Herdr tooling). This harness assumes `limen` / `herdr` / `gh` / Codex are available on your Mac PATH.

## Quick start

```bash
git clone https://github.com/lmiadowicz/startup-harness-codex.git
cd startup-harness-codex
bash setup.sh                         # tool checks + limen URL
bash setup.sh /path/to/your-product   # copy scripts into product .agents/delivery/scripts
export PRODUCT_ROOT=/path/to/your-product
bash "$PRODUCT_ROOT/.agents/delivery/scripts/status-dump.sh"
# macOS optional:
bash "$PRODUCT_ROOT/.agents/delivery/scripts/install-launchd.sh"
```

## What you get

| Path | Purpose |
| --- | --- |
| `.agents/delivery/scripts/` | `orchestrate.sh`, `review-and-label.sh`, `status-dump.sh`, `happy-path-smoke.sh`, `install-launchd.sh` |
| `.agents/delivery/PLAYBOOK.md` | Quality bar, Done-when, max 1–2 jobs, optional auto-merge label |
| `.agents/delivery/TICKET-TEMPLATE.md` | In / Out / Forbidden + Done-when |
| `docs/pstack.md` | How to use pstack (`to-spec` / `to-tickets` / `architect`) — clone upstream, do not vendor whole monorepo |
| `setup.sh` | Checks limen / herdr / gh / Codex; prints limen URL; installs scripts into a product repo |
| `scripts/render-charts.py` | Rebuild TARGET spider (matplotlib; optional `--mega-card`) |
| `vendor/mega-card/` | Vendored chart skill (attribution below) |
| `charts/` | Embedded PNG charts for the README |

## Charts (TARGET / design bar)

> **CRITICAL:** Charts showing **100%** are a **TARGET / design bar**, **NOT** a measured assessment score. Do **not** claim measured 100% / ORC 100%.

### TARGET 100% (aspirational)

![TARGET 100% design bar](charts/target-100.png)

### Codex-only path (design emphasis for this repo)

![Codex-only path chart](charts/codex-only.png)

### Matplotlib rebuild of TARGET (from `scripts/render-charts.py`)

![TARGET matplotlib](charts/target-100-matplotlib.png)

Rebuild:

```bash
python3 -m venv .venv && .venv/bin/pip install matplotlib
.venv/bin/python scripts/render-charts.py
# optional FUT card via Chrome:
.venv/bin/python scripts/render-charts.py --mega-card
```

## Credits

- **Limen:** get limen from https://mega.dev/autonomous-product-development — you can download Limen there.
- **Charts / mega-card skill:** https://github.com/piotrkrych2/Random-Skills — credit **piotrkrych2 / mega-card** for FUT card + 24-spoke spider charts (vendored under `vendor/mega-card/`).
- **pstack quality bar (optional):** Lauren Tan / [poteto](https://x.com/poteto) style — see [open-pstack](https://github.com/ericlitman/open-pstack) and `docs/pstack.md`. Keep LICENSE notices if you package anything from open-pstack.

See also `ATTRIBUTION.md`.

## Related

- Sibling harness with Grok Bot token-budget rules: [`startup-harness-grok-codex`](https://github.com/lmiadowicz/startup-harness-grok-codex) (independent repo, own history).

## License

Scripts and docs in this repo: use freely for your product harness. Vendored `vendor/mega-card/` retains upstream attribution. Upstream limen / pstack / Codex remain under their own terms.

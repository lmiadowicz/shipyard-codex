# How it works (Codex + Limen)

Flow: **Board (NOW / NEXT / PARK) → Tickets (Done-when) → limen / Pi workers → Codex → Review → Merge**.

Polished walkthrough: open [orchestration-animation.html](orchestration-animation.html) (also embedded from the README).

## Loop

1. **Board** — keep at most 1–2 jobs in NOW; NEXT is queued; PARK is deferred.
2. **Tickets** — every card has In / Out / Forbidden + falsifiable **Done-when** (see `TICKET-TEMPLATE.md`).
3. **Workers** — `limen` / Pi agents implement; prefer finishing over opening five half-PRs.
4. **Codex** — coding agent inside the worker path.
5. **Review** — Reviewer (+ Taste when UI) PASS / HOLD / FAIL with act-ons; evidence under `.verification/evidence/`.
6. **Merge** — owner / coordinator after clean PASS (optional `delivery:reviewer-pass` auto-merge when CI green).

## Install

Primary installer is Mac + VPS friendly shell:

```bash
bash setup.sh
bash setup.sh /path/to/your-product
```

## Charts

Primary spider charts are **MEASURED** (ORC **65** Codex-only). See [chart-traits.md](chart-traits.md). TARGET/90 live only under `charts/archive/`.

## pstack

Optional quality bar — [pstack.md](pstack.md). Do not vendor the full monorepo.

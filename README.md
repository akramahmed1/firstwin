# FirstWin

Small businesses winning big federal contracts, surfaced from free public data.

Every week the US government awards billions in contracts. Buried in that public data are first-time winners: small firms landing their first seven and eight figure awards. Nobody tells their stories. This does.

## How it works

`govcon_feed.py` pulls recent $1M+ contract awards carrying small-business set-aside codes from the free USAspending.gov API (no key needed), approximates first-time-winner status from 5-year recipient history, scores story-worthiness, and writes a digest plus a draft X thread.

## Run it

```bash
pip install requests
python govcon_feed.py
```

Outputs: `digest-top10.md` (the ranked finds), `x-thread-draft.md` (draft thread, NOT posted), `run-summary.json` (machine-readable stats).

## Latest run

400 awards scanned, 2026-09-09 to 2026-10-09. Top finds: White Wolf Managed Services ($20.9M, State Dept), Koman Construction Management ($12.9M, DHS), Peachtree Lumber ($99.6M, USDA Hurricane Helene timber work).

## Honest limitations

- First-time-winner detection is approximate (name-matched, not UEI-based). Verify before claiming.
- Amounts are total obligated to date, including modifications.
- The USAspending v2 API has no true small-business filter; coverage is via set-aside codes, which misses small firms winning full-and-open competitions.

## Roadmap

UEI-based recipient history, corporate-family resolution, weekly cron with diffing so only new wins surface.

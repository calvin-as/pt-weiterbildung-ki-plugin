---
name: neue-stellen-verfolgen
description: Keep someone informed about new psychotherapy training positions in Germany with the PT-Weiterbildung connector. Use when someone asks what is new (neue Weiterbildungsstellen, neue Weiterbildungsstätten, wer nimmt jetzt Bewerbungen an), wants to be told about new positions for a place, Bundesland or Verfahren, or wants a recurring weekly or daily check instead of an e-mail alert.
---

# Neue Stellen verfolgen

`get_new_openings` reports what changed since a date: training sites that are new in the directory, sites
that now accept applications (open position, waiting list or speculative applications), and sites that
published new application details such as a next intake date.

## One-time question ("Was ist neu?")

1. Use the filters the person already gave (place and radius, Bundesland, Verfahren, Gebiet). Ask only if
   nothing narrows it down and they clearly care about one region.
2. Call `get_new_openings`. Without `seit` it covers the last 7 days; pass an earlier date when they ask
   about a longer period (at most 180 days).
3. Report briefly, grouped as in the result: new sites, applications now possible, new application details.
   Give the detail link for each. If nothing changed, say so in one sentence.

## Recurring check

When the person wants to be kept informed:

1. Agree on the filters once and repeat them back.
2. If this assistant can run scheduled or recurring tasks, offer to set one up (for example weekly on Monday
   morning) whose prompt calls `get_new_openings` with exactly these filters and `seit` set to the previous
   run's date. Each result names that date in `naechste_abfrage_seit`.
3. In each run, report only the changes; if there are none, a one-line "nothing new" is enough.
4. If scheduled tasks are not available, offer the free e-mail alert instead: the result contains its link
   (`alert_url`, https://www.pt-weiterbildung.de/alert).

## Notes

- New sites appear after a short review window (a few hours) so that faulty imports can be stopped.
- Application status comes from the sites or from checks of their websites; suggest confirming with the site
  before applying.

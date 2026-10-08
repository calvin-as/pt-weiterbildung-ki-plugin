---
name: fragen-zur-weiterbildung
description: Answer questions about the psychotherapy specialist training in Germany (Psychotherapie-Weiterbildung after the Approbation, PsychThG reform 2020) with sources from pt-weiterbildung.de. Use for questions on how the five-year training is structured (ambulant, stationär, institutionell), pay and salary of PiW, financing, how to apply, the transition from the old Ausbildung, or how many training sites exist per Bundesland. Not for finding specific sites; use weiterbildungsplatz-finden for that.
---

# Fragen zur Psychotherapie-Weiterbildung beantworten

## Steps

1. Call `search_guides` with the question in a few keywords (German or English).
2. Read the best matching article with `get_guide` and the `slug`. Short FAQ answers in the search result are
   often enough for simple questions.
3. For numbers (how many training sites, per Bundesland, per Verfahren, share with open positions), call
   `get_statistics`, with `bundesland` when the question is about one state.
4. Answer in the person's language, briefly, and link the article or the numbers page you used. Give the date
   of the data ("Stand") for numbers.

## Care points

- Rules differ between Landespsychotherapeutenkammern (each has its own Weiterbildungsordnung). Say so when a
  detail depends on the state, and point to the Kammer for binding answers.
- Do not estimate salaries or fees beyond what the guide states; pay depends on the employer and the
  collective agreement.
- When the person wants to act on the answer (find a place, apply), offer to search with
  `search_training_sites`.

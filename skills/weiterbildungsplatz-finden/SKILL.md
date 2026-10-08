---
name: weiterbildungsplatz-finden
description: Find a training position for the psychotherapy specialist training in Germany (Weiterbildungsstelle, Weiterbildungsplatz, Weiterbildungsstätte) with the PT-Weiterbildung connector. Use when someone with an Approbation, a master's degree in psychotherapy, or a PiW (Psychotherapeut:in in Weiterbildung) asks where they can do or apply for their Weiterbildung, by city, postal code, region or Bundesland, by Verfahren (Verhaltenstherapie, tiefenpsychologisch fundiert, analytisch, systemisch) or by patient group (Erwachsene, Kinder und Jugendliche).
---

# Weiterbildungsplatz finden

The PT-Weiterbildung connector searches pt-weiterbildung.de, which combines the official lists of accredited
training sites from all 16 Landespsychotherapeutenkammern and updates them daily.

## Steps

1. Use what the person already said. Ask only for what is missing and changes the result: where (city, postal
   code or Bundesland), which Verfahren, and whether they want to work with adults or children and adolescents.
   If they give no place, search by Bundesland or Germany-wide rather than asking twice.
2. Call `search_training_sites`:
   - `ort` with the city or 5-digit postal code, `umkreis_km` 30 by default; use 50 to 80 km in rural areas or
     when fewer than three sites come back.
   - `verfahren`, `gebiet`, `versorgungsbereich` (ambulant, stationär, institutionell) only when the person named them.
   - `nur_bewerbung_moeglich: true` when they want places they can apply to now.
3. Present a short list: name, town and distance, Verfahren, application status, and the detail link. Explain
   the status in plain words:
   - "Stellen offen": the site reports open positions.
   - "Interessentenliste": no position right now, but a waiting list.
   - "Initiativbewerbung möglich": speculative applications are welcome.
   - "Derzeit keine offene Stelle": no position at the moment.
   - "unbekannt": the site has not reported a status yet; contacting it directly is the next step.
4. For the sites the person picks, call `get_training_site` with the `id` and give the application route,
   next date, contact, part-time options, pay and fees where known.
5. Close with the practical next step: apply or ask the site directly, because availability changes quickly.
   If they want to hear about new positions later, use the skill `neue-stellen-verfolgen`
   (`get_new_openings`, recurring check or the free e-mail alert at https://www.pt-weiterbildung.de/alert).

## If nothing fits

- Widen the radius, drop the narrowest filter, or check neighbouring Bundesländer.
- Some Bundesländer have published few or no lists yet; the result notes say so and name the responsible Kammer.

## Background worth knowing

- The Gebietsweiterbildung is the five-year specialist training after the Approbation (new law since 2020).
  It combines ambulant, stationär and institutionell sections. A Bereichsweiterbildung is an add-on
  qualification for those who already hold a specialist title; search it only when asked
  (`weiterbildungstyp: "Bereichsweiterbildung"`).
- The Kammer lists are authoritative for accreditation. Application status comes from the sites themselves or
  from checks of their websites and carries its own date.

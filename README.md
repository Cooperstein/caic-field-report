# CAIC field report — design concept

A working prototype of the backcountry observation report form for the
[Colorado Avalanche Information Center](https://avalanche.state.co.us), developed
alongside Avalanche Canada.

**Live page:** https://cooperstein.github.io/caic-field-report/

> **Draft.** This is a design exploration, not official CAIC guidance and not a live
> form. Nothing entered on the page is submitted anywhere.

## What is here

A single self-contained `index.html` — no build step, no dependencies. Open it
locally or view the published page.

**The form.** The proposed field report: contact, location, date, photos, field
notes and red flags. Three fields are required — location, date, and what you
observed. Everything else is one tap.

**Reveal modes.** A control at the top switches how optional detail is offered:

- *Link, fixed slot* — one permanently reserved row whose label changes with what
  was reported. The page never changes length.
- *Link, appears* — the contextual row appears when it becomes relevant.
- *Fields inline* — reporting an avalanche injects the avalanche fields directly
  below; reporting that someone was caught injects the avalanche fields and then
  the group details.

**Reveal patterns.** Five approaches side by side with a live block-height readout,
so the layout shift each one causes is visible rather than argued about.

**Privacy patterns.** Four ways to surface the publish-or-anonymous choice, with a
table mapping them onto the three booleans the API already stores
(`is_anonymous`, `is_anonymous_location`, `is_locked`).

**Field audit.** Every field judged on one test: is what it returns worth what it
costs the reporter to give.

## Design principles behind it

- Reporting a red flag must never add a required field. A form that charges people
  for honesty will quietly train them to stop being honest.
- Never ask a person for something an instrument already measures better.
- Precision you cannot collect is worse than none — two options someone can answer
  honestly beat five they cannot.
- Ask for identity and contact details around the report, never as a toll gate in
  front of it.

## Editing

Everything lives in `index.html`. Pushing to `main` redeploys the page.

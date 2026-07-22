# Call-Centre Booking Rate Analysis — Anonymised

A worked example of analysing appointment-setting performance in an outbound and
inbound phone team, covering an 8-day window: **14,851 calls, 2,301 connected,
690 appointments booked, 54 agents.**

This is a **fully anonymised public release.** Agent names are replaced with codes
(`Agent 01`…`Agent 56`), team names with letters, and all internal call links have
been removed. Every number is unchanged from the source analysis.

## The reports

| File | What it shows |
|---|---|
| [`asr-booking-rate-dashboard.html`](asr-booking-rate-dashboard.html) | Booking rate at company, team and agent level, with daily / weekly / monthly views, inbound-outbound filters and a minimum-sample control. |
| [`asr-call-coaching-pack.html`](asr-call-coaching-pack.html) | What separates a booked call from a declined one, measured across 1,347 transcripts. |
| [`asr-objection-rebuttal-playbook.html`](asr-objection-rebuttal-playbook.html) | The objections customers actually raise — taken from their own words rather than the rep's after-call disposition — each with a rebuttal. |

Each file is self-contained: no build step, no dependencies, no external assets.

## What the analysis found

**A reporting bug was inflating the headline number.** The internal report showed a
43.56% booking rate. Measured consistently over the same window it was **29.7%**
against a 40% target. The denominator — count of calls over 90 seconds — was not
being populated for recent days while the numerator kept accruing, which also
produced weekly rates above 100%. Any figure over 100% is worth chasing; it is
almost always a denominator that stopped updating.

**Inbound and outbound are different businesses sharing one metric.** Outbound
connects on 4.9% of dials but books 36.4% of those connections. Inbound connects on
58.6% and books 25.3%. Because teams are organised by channel, the team league table
was mostly re-describing the channel split. Every agent at or above the 40% target
was outbound; no inbound agent reached it. A single blended target manufactures
failure for one half of the floor.

**One behaviour dominated everything else.** Naming a specific day and clock time
("Monday at 3 o'clock", "11:20 or 11:40") appeared in **48% of booked calls and 3%
of declined ones** — a 15.6× gap, far larger than any other measured behaviour.
Empathy markers and entitlement framing ("this came with your purchase") appeared
*slightly more often in declined calls*, so the intuitive coaching advice — be
warmer, explain the value better — pointed the wrong way.

**The automated QA score did not predict the outcome it was assumed to.** Calls
carried an automated rubric score out of 10. The agents hitting target averaged
6.1; several scoring above 7.0 booked under 25%. The rubric measured customer-care
quality, which is a different job from appointment setting.

**The most winnable objection was the one being thrown away.** "Call me later"
accounted for 101 objections and was lost 32% of the time — not because customers
refused, but because reps accepted a vague window ("sure, I'll try you next week")
instead of converting it into a booked slot.

## Method

- **Numerator:** appointments counted as distinct customer email addresses per agent
  per day, from the booking form, rather than counting form rows — about 5% of rows
  were repeat bookings of an address already booked that month.
- **Denominator:** calls with talk time ≥ 90 seconds.
- **Transcripts** were split into rep and customer turns. Objections were detected
  from the customer's own wording, not the disposition the rep selected afterwards.
  A call counts as "asked again after the objection" only when the rep requested a
  booking in a turn *after* the customer's last objection.

### Limits worth stating

- One day is missing from the call export; it was the busiest of the period.
- Two teams appear with bookings but no call records, so no rate is computed for them.
- Weekly and monthly views are necessarily partial — the call window is 8 days.
- Agents with fewer than 30 connected calls are dimmed in the agent table; at that
  sample a rate has a confidence band wide enough to be misleading.

## Anonymisation

Names, team labels and internal call links were removed programmatically and the
output verified to contain no residual identifiers. The mapping between codes and
real people was never committed to this repository. Customer quotes are reproduced
without names, phone numbers or email addresses.

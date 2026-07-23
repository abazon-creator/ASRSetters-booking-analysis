# ASR Booking Rate Analysis

Analysis of the Performance Golf ASR phone team's appointment-setting
performance over an 8-day window: **14,851 calls, 2,301 connected,
690 appointments, 54 agents.**

> **This repository names individual employees alongside their performance
> figures, and it is public.** Published deliberately — see
> [Who is named](#who-is-named).

**Live site: https://abazon-creator.github.io/ASRSetters-booking-analysis/**

## The reports

| Page | What it shows |
|---|---|
| [Overview](index.html) | Headline numbers and the four findings that change what to do next. |
| [Booking Rate Dashboard](asr-booking-rate-dashboard.html) | Rate at company, team and agent level, with daily / weekly / monthly views, inbound-outbound filters and a minimum-sample control. |
| [Call Coaching Pack](asr-call-coaching-pack.html) | What separates a booked call from a declined one, measured across 1,347 transcripts. |
| [Objection & Rebuttal Playbook](asr-objection-rebuttal-playbook.html) | The objections members actually raise — from their own words, not the rep's after-call disposition — each with a rebuttal. |

## What the analysis found

**A reporting bug was inflating the headline number.** The Closer Report showed
a 43.56% booking rate for July. Measured consistently over the same window it
was **29.7%** against a 40% target. The denominator — calls over 90 seconds —
stopped updating on 20 July while appointments kept accruing, which also
produced weekly rates above 100%. Any figure over 100% is worth chasing; it is
almost always a denominator that stopped moving.

**Inbound and outbound are different businesses sharing one metric.** Outbound
connects on 4.9% of dials but books 36.4% of those. Inbound connects on 58.6%
and books 25.3%. Teams are organised by channel, so the team league table was
mostly re-describing the channel split. Every agent at or above target was
outbound; no inbound agent reached it. A single blended target manufactures
failure for one half of the floor.

**One behaviour dominated everything else.** Naming a specific day and clock
time appeared in **48% of booked calls and 3% of declined ones** — a 15.6×
gap, far larger than any other measured behaviour. Empathy markers and
entitlement framing appeared *slightly more often in declined calls*, so the
intuitive coaching advice pointed the wrong way.

**Discovery depth predicts the outcome.** Booking rate rises from 18% on calls
with under five questions to 84% on calls with thirty or more.

**The automated QA score did not predict what it was assumed to.** The agents
hitting target averaged 6.1/10; several scoring above 7.0 booked under 25%.
The rubric measures customer-care quality, a different job from setting.

**The most winnable objection was being thrown away.** "Call me later"
accounted for 101 objections and was lost 32% of the time — not because members
refused, but because reps accepted a vague window instead of booking a slot.

## Method

- **Numerator:** appointments counted as distinct member email addresses per
  agent per day, rather than counting form rows — about 5% of rows are repeat
  bookings of an address already booked that month.
- **Denominator:** calls with talk time of 90 seconds or more.
- **Transcripts** split into rep and member turns. Objections detected from the
  member's own wording. A call counts as "asked again after the objection" only
  when the rep requested a booking in a turn *after* the member's last objection.

### Limits

- 13 July is absent from the figures on this site.
- Two teams show appointments but no call records, so no rate is computed for them.
- Weekly and monthly views are partial — the call window is eight days.
- Agents with fewer than 30 connected calls are dimmed in the agent table; at
  that sample the confidence band is wide enough to mislead.

## Who is named

This site shows **54 named employees** with their individual booking rates, and
the coaching pack identifies specific agents as needing coaching. Team names are
real. This was published knowingly by the team's own management.

Removed before publishing: member names, email addresses, phone numbers, and all
internal Aloware call links (52 of them), which exposed contact and
communication IDs.

Member quotes are reproduced without any identifying detail. Some describe
health circumstances in the member's own words, included because they are the
objections reps have to handle.

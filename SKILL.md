---
name: roof-appointment-qualification
description: Use when the user pastes a roof inspection appointment call transcript, to extract and organize lead and qualification details for the setter, the inspector, and the team.
---

# Roof Appointment Transcript Extraction

The user is an appointment setter for PACC Solutions (roofing + insurance claims, Chicago area). They paste a call transcript (Spanish or English). Your job is to gather the details from it into a qualification summary. Accuracy matters more than polish: the inspector and team rely on it.

Output in English by default (Spanish only if asked).

The output ALWAYS has the same structure and the same order: Part 1 (Setter Review, for the user only), then Part 2 (Copy-Ready block, for the inspector and team). Never reorder, rename, merge, or skip sections or fields. If a field has no information, keep the field and write the neutral missing phrase (see below).

## Part 1: Setter Review (for the user only)

Timestamps [mm:ss] are allowed here, after key facts, so the user can verify quickly.

**Appointment**: date, time, inspector, how the inspector will contact the customer, reminder or caller-ID notes, solo inspection possible or not.

**Contact**: full name (fix speech-to-text spelling), phone (confirmed or not), email (as spelled; flag "verify spelling"), address and zip (normalized), language.

**Roof and damage (customer's own words)**: roof type, age and material, what the customer reported, when it started, what they did about it, signs mentioned, storm connection (what they said vs. what they only agreed to), roof access.

**Insurance**: company, claim status (filed, wants to file, none), whether the carrier was contacted about this damage, policy name and copy availability, deductible.

**Flags**: self-applied repairs or sealant, damage that may predate a storm, confusion during the call, time or date stated inconsistently, leading questions the customer only agreed to (write "customer agreed that...", not "customer reports..."), not the owner or policyholder, other contractor quotes or adjuster visits, no-show risk, caller-ID name mismatch, expectations the setter set that the inspector may need to reset.

### Missing information (with the reason)

For every checklist item without a usable answer, say WHY it is missing. Use exactly one of these labels per item:

- **NOT ASKED (setter missed it):** the question never came up in the call.
- **ASKED, NOT PROVIDED:** the setter asked, but the customer did not give a usable answer. Add the reason in a few words: didn't know, wasn't sure, declined, gave a vague answer, or answered a different question. Quote or paraphrase what the customer actually said.
- **ASKED, CONFLICTING:** the customer gave inconsistent answers (e.g., said one time, then another).

Be strict: a question counts as asked only if the setter actually asked it in the transcript. If the customer volunteered the information unprompted, it is provided, not missing. If the setter stated something and the customer only agreed, note it as "agreed, not stated."

Checklist items to check: phone confirmed, email confirmed, insurance company, claim filed or wants to file, policy name, policy copy availability, deductible and amount, date and time, inspector named, solo inspection possible, roof age and material, owner and policyholder status, interior damage, other contractor quotes or prior claims, storm date.

## Part 2: Copy-Ready block (inspector and team)

This block is pasted to the inspector and the team. It ALWAYS has exactly these four numbered sections, in this order, with exactly these fields in this order:

Rules for the whole block:
- No contact info, no appointment details, no setter-only flags.
- NO timestamps.
- No judgment of the setter. For anything missing, use a neutral phrase: "Not discussed on call, confirm on site", "Customer unsure", or "Customer declined to say." Never write "setter forgot."
- Plain text, short lines, no markdown tables, so it pastes cleanly into GHL or a message.
- Facts in the customer's reported terms. Do not state storm damage as confirmed; use "customer reports" or "customer agreed that."

1. ROOF AND REPORTED DAMAGE
Roof type: ...
Roof age and material: ...
Reported issue: ...
Timing: ...
Signs reported: ...
Self-applied repairs: ...
Storm connection: ...
Interior damage: ...
Roof access: ...
Other contractors or inspections: ...

2. INSURANCE INFORMATION
Company: ...
Claim status: ...
Carrier contacted about this damage: ...
Policyholder / owner: ...
Policy: ... (name, copy availability)
Deductible: ...

3. INSPECTOR NOTES
(One short paragraph, UNDER 200 CHARACTERS including spaces. See rules below.)

4. IMPORTANT DETAILS
Customer specifically mentioned:
- ...
Heads-up for the team:
- ...

### Rules for section 3, Inspector Notes

A single compact paragraph of recommendations for the inspector, based on what was said in the conversation. HARD LIMIT: under 200 characters including spaces and punctuation. Count the characters before outputting; if it is 200 or more, shorten it until it is under 200. No bullets, no sub-headings, no line breaks inside the paragraph.

- Tailor it to this call: roof type, the problem described, what the customer already tried, and the insurance situation. No generic text that ignores the transcript.
- Order of content: overall inspection appropriate to the roof type, then the specific areas the customer described (leak location, spots noticed), then a note on any self-applied repair (e.g., photograph the sealant), then the key things to look for (e.g., uplift, moisture, membrane failure), then the cause and claim determination.
- If the customer is interested in insurance help, end with the claim determination (e.g., "Determine storm cause and claim eligibility.").
- Base every item on something the customer said. Do not invent problems the customer never described. Phrase causes as things to check, never conclusions.
- Adapt to roof type: flat roofs get membrane, seams, ponding, flashing; shingle roofs get shingles, granule loss, flashing, vents; unknown type gets a general inspection.
- Items to confirm on site are already shown inside sections 1 and 2 with the neutral missing phrase, so do not repeat them here.

### Rules for section 4, Important Details

- Customer specifically mentioned: 2 to 5 short bullets restating the key facts the customer reported, in plain terms (what they did, what they still see, what they want).
- Heads-up for the team: practical details the inspector and team should not miss, stated neutrally. Examples: the customer applied a repair that may affect the claim; the customer understands storm damage is typically covered and expectations may need managing if the cause is not storm-related; the customer asked for a text reminder because he ignores unknown numbers, and which company name will show on the call; scheduling flexibility; language spoken; other decision-makers; other contractors involved. Include only items relevant to this call.

## Accuracy rules

- Only report what is in the transcript. Do not invent roof age, deductible, claim status, storm dates, or customer intentions.
- Separate stated facts from inference. Possible causes appear in the Setter Review (labeled "possible, not confirmed") and as things to check in Inspector Notes; never as established fact.
- Do not add mindset or sentiment claims unless clearly said. Observable demeanor (cooperative, retired and flexible) is fine.
- Fix obvious transcription errors in names, numbers, and company names, and say you did.
- Keep everything scannable. No filler, no repeating the transcript.

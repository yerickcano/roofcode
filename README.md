# Roof Appointment Qualification (Claude Skill)

Turns a roof inspection call transcript (Spanish or English) into a consistent qualification summary for setters, inspectors, and the team.

## Output
1. **Setter Review** (private): appointment, contact, damage, insurance, flags, and missing info. Each gap is labeled *not asked* or *asked, not provided*.
2. **Copy-Ready block** (shared), always in this order:
   1. Roof and Reported Damage
   2. Insurance Information
   3. Inspector Notes (under 200 characters)
   4. Important Details

## Usage
Put `SKILL.md` in a folder named `roof-appointment-qualification`, upload it as a Claude skill, then paste a call transcript.

## Rules
- Only facts from the transcript
- No timestamps in the shared block
- Neutral wording for missing info
- English output by default

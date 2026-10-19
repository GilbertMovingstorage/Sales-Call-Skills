# Gilbert Moving & Storage — Sales Call Skills

This repository contains the **Moving Company Call Audit** skill for reviewing sales and customer-service calls at Gilbert Moving & Storage (GMS).

## What the skill does

Use the skill to audit call transcripts, recordings, or call notes; score sales calls against the GMS 100-point scorecard; coach representatives with specific evidence; review service and claim-related calls; and assess AI receptionist intake and handoff quality.

It supports:
- Individual call audits and coaching.
- Multi-call and weekly team reviews.
- Call outcome classification and follow-up action lists.
- Critical-flag reporting for important process or policy misses.
- Calibration against feedback from Jesse or a sales manager.

## Skill location

- **Skill file:** [`moving-company-call-audit/SKILL.md`](moving-company-call-audit/SKILL.md)

## When to use it

Use this skill when you provide a call transcript, audio/video recording, or call notes and want to:
- Audit, score, grade, or coach a sales representative.
- Review customer-service, service-recovery, or claims conversations.
- Evaluate AI receptionist data capture and human handoff.
- Compare multiple calls or summarize recurring team coaching needs.
- Identify booking opportunities and follow-up actions.

## Call types covered

The skill classifies calls into these groups:

| Type | Call category | Primary focus |
|---|---|---|
| A | New lead — local | Book the move |
| B | New lead — long distance | Schedule an in-home or virtual estimate |
| C | Outbound follow-up | Book, schedule an estimate, or secure an agreed follow-up |
| D | Repeat or referred customer | Advance the booking |
| E | Existing booking | Resolve the question and confirm the next step |
| F | Service recovery or claim | De-escalate, explain options, and establish ownership |
| G | Post-move survey | Collect feedback and, where appropriate, request a review or referral |
| H | AI receptionist | Check intake accuracy and handoff |
| I | Vendor or non-customer | Evaluate the interaction and protect company interests |

Sales calls use the fixed 100-point scorecard in the skill. Service-focused calls use the relevant checklist instead.

## How to use the skill

1. Open the skill file linked above and follow the installation instructions for the AI assistant or environment where you use skills.
2. Start a conversation with a clear request, such as:
   - “Audit this Gilbert Moving & Storage sales call using the GMS scorecard.”
   - “Review these five calls and summarize each rep's coaching priorities.”
   - “Evaluate this AI receptionist call for data accuracy and handoff.”
   - “Review this service-recovery call and identify the best next response.”
3. Provide the transcript, recording, or notes. Include the representative's name and call date if known.
4. Review the findings and verify any policy-sensitive details against current GMS procedures before acting.

For recordings, the skill describes a local transcription workflow using the included `scripts/transcribe.py` and `scripts/build_doc.py` commands. Those scripts must be present in the environment and their dependencies installed; this repository currently contains the skill file only unless those files are added separately.

## Audit principles

The skill instructs the auditor to:
- Review the complete available call before scoring.
- Use call evidence and timestamps where available; never invent details.
- Ignore transcription artifacts and acknowledge incomplete recordings or transcripts.
- Separate critical flags from the scorecard category weights.
- Distinguish the representative's performance from the call outcome.
- Mark genuinely inapplicable items N/A and explain score normalization.
- Treat company rates and policies as reference values that must be verified against current information.
- Avoid ranking employees solely by AI-generated scores for employment decisions.

## Important note

This repository documents a call-review workflow; it is not a substitute for current company policy or manager judgment. Confirm time-sensitive rates, fees, payment rules, and procedures with GMS before relying on them.

## Repository contents

```text
Sales-Call-Skills/
└── moving-company-call-audit/
    └── SKILL.md
```

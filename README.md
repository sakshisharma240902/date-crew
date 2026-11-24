# Pre-send compatibility check (prototype)

Prototype for The Date Crew Product Growth Assessment, Part 3.

**Problem:** about 35% of rejected profiles were rejected for reasons already in the client's stated preferences. This tool checks a candidate against those preferences before the profile is sent.

## How it works

For each client and candidate, the check runs both ways (client's preferences against the candidate, and the candidate's preferences against the client).

| Result | Meaning |
|---|---|
| Warning | A must-have preference (e.g. smoking, children) is broken. Sending requires an override reason. |
| Flag | A soft preference (e.g. age range, height, city, education) is missed. |
| Can't verify | The profile lacks the data. Never counted as a pass. |
| Clear to send | No conflicts found. |

Each candidate also gets a match score: the share of checkable preferences met, with must-haves weighted double. Every send, and every override reason, is logged.

## Notes

- All data is mocked.
- Fields marked "read from bio" are hard-coded. In a real build, an LLM would extract these from free-text bios, and the rules would still make the decision.
- Single file, no dependencies. Open `index.html` in a browser.

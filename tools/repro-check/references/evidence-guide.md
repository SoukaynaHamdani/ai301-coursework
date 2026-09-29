# Evidence guide: where proof lives in a reproduction package

## Environment

- Where it lives: In an eval bundle, the environment record line at the top of the repro report, compared against the issue context and the repo-facts block. In live mode, the environment section specified in the student's draft comment or the repo's bug report template.
- What good looks like: The versions named match what the issue targets, or the difference is explicitly called out and explained.
 
## Steps

- Where it lives: In an eval bundle, the reproduction steps section of the repro report, read against the repo-facts block. In live mode, the steps listed in the student's draft comment tested against a fresh clone of the codebase.
- What good looks like: The steps list exact terminal commands in chronological order that a stranger can execute sequentially to reach the target state without missing prerequisites.

## Behavior shown

- Where it lives: In an eval bundle, the terminal output excerpt, exit code, or logs in the repro report's behavior section, read against the issue's description. In live mode, the output logs in the student's draft compared with the issue thread.
- What good looks like: The observed artifact's outcome strictly matches the issue's failure description, or honestly evidences a verified cannot-reproduce state.

## Honesty

- Where it lives: In an eval bundle, the initial claim comment read against the actual results in the repro report. In live mode, the student's draft comment compared with the execution logs.
- What good looks like: The report states exactly what happened without exaggeration, and an inability to reproduce the issue is reported transparently as such rather than faked.

## Comms

- Where it lives: In an eval bundle, the claim comment and report text read against the repo's stated templates and contribution policy. In live mode, the student's draft comment in the issue thread.
- What good looks like: The text uses natural language without bot-like phrasing or excessive praise, and respects project norms and AI-use disclosure requirements.
## Checks
| Check | Evidence | Pass condition | Weight |
| `env-recorded` | The environment record at the top of the repro report, compared against the repository's bug report template. | Pass when: the report explicitly names the exact tool version and operating system requested by the template, or provides a factual explanation for any mismatch. | `required` |
| `steps-followable` | The reproduction steps section in the report read against a fresh clone of the repository. | Pass when: the steps list the exact terminal commands in chronological order such that a stranger executing them sequentially arrives at the target state without missing prerequisites. | `required` |
| `behavior-matches` | The terminal output excerpt or exit code in the report's behavior section read against the original issue's described failure. | Pass when: the observed artifact's outcome (such as the exit code or panic message) strictly matches the issue's failure description, or honestly evidences a verified cannot-reproduce state. | `required` |
| `claim-honest` | The initial claim comment posted on the issue prior to reproduction work. | Pass when: the claim states a realistic next artifact (such as a repro report) rather than a false timeline or empty promise, and transparently flags if it is a first contribution. | `required` |
| `conventions-respected` | The tone and formatting of the claim and report text read against the repository communication style. | Pass when: the text uses natural language without bot-like phrasing or excessive praise, avoiding structure-shaped formatting checks while respecting project norms. | `preferred` |

## Verdict rule

accept if every required check passes; preferred checks never change the verdict; any unclear grade counts as a fail.

 
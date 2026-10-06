# Voice guide: how I talk upstream

## Who I am in threads

I am an engineering student and developer contributing practical bug fixes and reproductions. I state my technical scope plainly, focus strictly on reproducible code evidence, and never pretend to be a senior maintainer or an automated bot.

## Rules I write by

### Rule: claim-before-fix

- The initial comment must state a realistic next artifact rather than making grand promises or false timelines.
- Wrong: "I am a top expert and I will completely rewrite your repository architecture by tomorrow morning."
- Right: "I am investigating this issue and will post a reproduction report with logs shortly."

### Rule: concise-evidence

- Keep technical explanations direct and grounded in output logs, avoiding excessive praise or filler words.
- Wrong: "Hello amazing team! Thank you so much for this incredible library, it is literally the best thing ever created."
- Right: "I reproduced the issue on version 1.20.0; here are the exact steps and exit code."

### Rule: honest-disclosure

- Transparently disclose the status of the environment and any limitations or first-time contributions without hiding facts.
- Wrong: "Everything passed smoothly on all systems without any issues whatsoever."
- Right: "I could not reproduce the panic on macOS, but here are the exact logs from Linux where it failed with exit 2."

## Things I never post

- Empty promises or fake timelines about when a fix will be ready.
- Excessive flattery, hype, or robotic corporate phrasing.
- Claims about code behavior that are not backed up by local terminal outputs or logs.
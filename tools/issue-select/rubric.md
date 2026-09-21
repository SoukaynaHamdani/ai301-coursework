# Rubric: is this a good first issue?
 

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | "last 5 default-branch commits" or "maintainer first-response sample" in Repo facts, and Comments section | a maintainer commented, committed, or merged a PR within the last 90 days | required |
| repo-in-use | "latest release" or "last push to any branch" in Repo facts | the last commit or release happened within the last 6 months | preferred |
| scope-fits | issue body and Comments section | accept standard bugs, feature tweaks, and specific lists of fixes; reject ONLY explicit "umbrella", "epic", or open-ended support questions | required |
| unclaimed | "assignees:" and "linked PRs:" in Repo facts | no official assignee and no open or merged PRs (ignore claim comments from other students) | required |
| policy-allows-ai | "contribution policy" line in Repo facts | the policy does not state an outright ban on AI-generated code (silence or conditions pass) | required |

## Verdict rule
Accept the issue only if every `required` check passes. A `?` (unclear) on a required check counts as a fail. The `preferred` checks never change the final verdict; they only rank the accepted issues.

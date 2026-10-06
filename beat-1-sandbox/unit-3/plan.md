# Plan: Fix missing `file_structure` key in `GitHubTool._fetch_repo_metadata()`

Issue: #18 — https://github.com/codepath/pathreview-ai301-fa26-s1/issues/18

## Diagnosis

`RepoAnalyzer.parse()` fails to detect tests and CI (`has_tests` and `has_ci`), so both default to `False`. In my reproduction evidence for Issue #18, calling `GitHubTool._fetch_repo_metadata()` returns a metadata dictionary that completely lacks the `file_structure` key:

```text
Keys returned: ['name', 'description', 'primary_language', 'star_count', 'fork_count', 'open_issues_count', 'last_commit_date', 'has_readme', 'topics', 'homepage']
'file_structure' in data? False
```

The root cause is an omission in `GitHubTool._fetch_repo_metadata()`: the repository's directory contents are never queried and added to the metadata payload. `RepoAnalyzer.parse()` relies directly on this key, so its absence breaks test and CI detection upstream.

## Scope

**In scope:**

- Update `GitHubTool._fetch_repo_metadata()` to fetch the repository's directory listing and populate the `file_structure` key.
- Verify only (no edits) that `RepoAnalyzer.parse()` correctly consumes the structured tree data.
- Add unit tests verifying that `file_structure` is present in the metadata output.

**Not in scope:**

- Refactoring unrelated tools or changing the GitHub API wrapper's authentication logic.
- Redesigning the dashboard UI or changing reporting formats.

## Files to touch

- `agent/tools/github_tool.py` (modify: fetch the file structure)
- `ingestion/parsers/repo_analyzer.py` (verify only, no changes)
- `tests/test_github_tool.py` (new file: tests for metadata generation)

## Approach

1. Locate `GitHubTool._fetch_repo_metadata()` in `agent/tools/github_tool.py` and add file-tree fetching so the returned metadata includes `file_structure`.
2. Verify that `RepoAnalyzer.parse()` in `ingestion/parsers/repo_analyzer.py` consumes the new key without raising structural exceptions.
3. Add regression unit tests in `tests/test_github_tool.py` checking that `file_structure` is present and that the test and CI flags change from `False` to `True`.

## Test plan

I re-run my unit 2 repro steps against `codepath/pathreview-ai301-fa26-s1`.

**Before the fix (bug case):** the extraction returns metadata lacking `file_structure`:

```text
'file_structure' in data? False
has_tests: False, has_ci: False
```

**Expected after the fix (control case):** re-running the extraction and analysis pipeline produces:

```text
'file_structure' in data? True
has_tests: True, has_ci: True
```

## Risks and unknowns

- **API rate limiting:** fetching repository contents increases GitHub API call volume. I will limit this by caching tree responses where appropriate.
- **Large repositories:** deep trees can return massive payloads, so traversal will be bounded to the root level and the relevant test and workflow paths.

## Deviations
No deviations. The implementation followed the planned approach exactly, and the API root contents fetching successfully populated the file_structure key.
 

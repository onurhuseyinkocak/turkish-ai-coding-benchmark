# Methodology

This benchmark evaluates whether an AI coding workflow can help a Turkish builder move from prompt to usable software proof.

## Score Scale

- `0`: no usable output.
- `1`: partially relevant but unsafe or incomplete.
- `2`: useful outline, not directly executable.
- `3`: usable with manual fixes.
- `4`: good output with minor gaps.
- `5`: production-ready for the task scope.

## Dimensions

- Correctness: does it solve the task?
- Build and test readiness: can the output be run, checked or verified?
- Security awareness: does it avoid unsafe defaults and secret leakage?
- Maintainability: is the output understandable and easy to revise?
- UX quality: does it produce usable interface or workflow decisions?
- Turkish context quality: does the Turkish copy sound natural and locally relevant?
- Autonomy: does the tool complete the task with minimal manual rescue?

## Publication Rules

No leaderboard is published until:

- Every active task has frozen fixtures.
- Every compared tool has complete runs for the same task set.
- Every public result row includes prompt, tool version/date, output link or commit, reviewer notes and audit date.
- Every public result row has `published=true`, `reviewer_count >= 2` and non-empty `audited_at`.

## Disclosure

This benchmark is maintained by Vibe Coding Turkey. It is not a paid ranking and not a universal tool leaderboard. Tool maintainers and community members can submit reproducible results through issues or pull requests.

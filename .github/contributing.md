# Making commits
Sign-off your commits ([Git flag](https://git-scm.com/docs/git-commit#Documentation/git-commit.txt---signoff)), [read here about DCO obligations](https://developercertificate.org/).
Sign commits where possible, [learn more about that here](https://docs.github.com/en/authentication/managing-commit-signature-verification/signing-commits).
Prefer to use [Conventional Commit style](https://www.conventionalcommits.org/en/v1.0.0-beta.2/).
If present, e.g. prettier, cargo fmt, use the formatter.
Try to keep each PR bound to a single feature or change, multiple bug fixes may be fine in some cases. This is to avoid your PR getting stuck due to parts of it having conflicts or other issues.

# Merging Pull Requests
All PR titles must use [Conventional Commit style](https://www.conventionalcommits.org/en/v1.0.0-beta.2/) and will be squash merged!
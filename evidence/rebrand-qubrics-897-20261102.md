# GitHub live references — MailWizz extension

Part of qubrics/qubrics#897, spec A15. Source-only PR; no merge, release publication, deployment or GitHub settings change.

Composer support source and README raw-asset/release URLs now use `qubrics/mailwizz-smtp-proxy`; SDK source points at `qubrics/qubrics-sdk`. Existing package, extension, version and release-asset names and product/service hosts remain unchanged. Historical changelog entries are preserved.

Checks: `composer test` passed with 78 tests and 235 assertions; `git diff --check` and the live old-owner/repository reference scan passed. No tests or test harnesses were added. Existing local Composer dependencies were reused through a task-owned vendor symlink.

Local log: control-plane MAIN `.claude/artifacts/rebrand-qubrics-897/mailwizz-check.log`.

Existing PR CI runs PHP 8.0 and 8.3; release packaging stays tag-only and unexecuted. Independent review is coordinated across the batch; no review-settled claim is made here.

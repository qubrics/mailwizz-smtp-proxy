# MailWizz v0.3.1 release candidate for docs75

Candidate only; tag/release publication remains held for Ops ASK. Label source PR5 is merged at `9e4698668bd8a276445c404f3bebebb560029d25`; PR CI43986647255 and main CI43987089248 passed PHP8.0/8.3, each78tests/235assertions. Source rollback: revert that merge.

The latest public release is still v0.3.0. Proposed next patch v0.3.1 contains only its approved display-label correction plus the seven correlated release metadata/changelog locations required by AGENTS.md. All five PHP version docblocks, the extension version property, existing metadata test's expected version and newest changelog section agree. No new test/assertion, dependency, runtime logic or compatibility ID change is introduced by this release-preparation diff.

`composer test` on this candidate exited0: **78 tests,235 assertions**, no skips reported. `git diff --check` exited0. Original MAIN checkout remains clean; isolated branch `agent/rebrand-qubrics-docs75-release` starts from merged9e469866. Raw log: MAIN `.claude/artifacts/rebrand-qubrics-docs75/release-candidate-tests.log`.

Build the review ZIP using the existing `.github/workflows/release.yml` recipe: copy `SendmuxWebApiExt.php`, `composer.json`, `LICENSE`, `README.md`, `CHANGELOG.md` and `backend/common/customer/frontend` below `sendmux-web-api/`, then zip that directory as `sendmux-web-api.zip`. Neither agent state, tests, dependencies nor this evidence file enters the package. The GitHub tag workflow must still pass both PHP jobs before publishing its own generated asset. Local ZIP bytes are a review candidate; do not claim its SHA256 will equal a future runner's ZIP, whose timestamps/platform metadata may differ. Compare package member content to the approved candidate when verifying the published asset.

Named publication rollback anchor: existing [v0.3.0 release](https://github.com/qubrics/mailwizz-smtp-proxy/releases/tag/v0.3.0), asset `sendmux-web-api.zip`, SHA256 `2b396606632f589d83bd85d175f6bf530827b77766acd044fcc796383f4c13c5`, downloaded and verified before the access stop. Restore that previous extension package if required, preserving its unchanged extension/type identities and saved configuration; revert source/release metadata through ordinary PRs. A published tag/release remains a historical public event, so source revert alone cannot retract downloaded ZIPs.

Release GO must name the immutable candidate commit, next tag v0.3.1, exact expected artifact and rollback. Until that GO, no tag push, GitHub Release creation, live MailWizz installation or docs publication occurs. After authorised publication, verify actual ZIP contents and the picker readback, then update docs75's two exact labels from that measured producer fact.

Polish pass: skipped — exact technical UI-label mapping and version metadata only. Existing changelog structure and earlier entries preserved.

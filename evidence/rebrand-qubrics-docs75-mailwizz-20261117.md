# MailWizz picker labels for docs75

Part of qubrics/docs#75 and the approved rebrand spec. Ops assigned this producer slice to docs75 on17November2026: only extension/picker display labels change, compatibility IDs stay, green CI permits merge; tag/release publication returns to Ops as a separate ASK.

Origin confirmed `https://github.com/qubrics/mailwizz-smtp-proxy.git`. Isolated branch `agent/rebrand-qubrics-docs75` starts at main `23932f4e7bbc2ef732394be69be1b6b9855bca41`. Source checkout stays clean. Latest GitHub release is `v0.3.0`, asset `sendmux-web-api.zip`, SHA256`2b396606632f589d83bd85d175f6bf530827b77766acd044fcc796383f4c13c5`.

## Source change

`SendmuxWebApiExt.php` public name now returns `Qubrics Sending API`. `DeliveryServerSendmuxWebApi::getTypeName()` returns `Qubrics Web API` through the existing `servers` translation category. README's two matching UI instructions use those exact names. Other prose and metadata are unchanged.

Canonical seam: local upstream MailWizz source `mailwizz-pure/apps/backend/views/delivery_servers/list.php:258` instantiates the mapped delivery-server model and calls its `getTypeName()` for the picker; customer list uses the same instance method. `apps/common/models/DeliveryServer.php:1058` normally derives the label from the stable type. Overriding that existing method changes the display without renaming the key. Local source is MailWizz2.7.3; this is source-path verification, not a live customer-installation proof.

No mapping/storage key, class, route, API endpoint, webhook/signature/header/key identifier, credential behaviour or ZIP identity changes. Version metadata remains0.3.0 in this source-only label PR. No version or tag was invented/published.

## Measured verification

`composer test` before and after the edit each exited0: **78 tests,235 assertions**, no skipped tests reported. `git diff --check` exited0. Existing lockfile/dependencies reused in the isolated worktree; no test or harness added/altered.

Direct execution of the actual extension/model through the existing bootstrap/stubs exited0:

```text
extension=Qubrics Sending API
picker=Qubrics Web API
compat_type=sendmux-web-api
endpoint=https://smtp.sendmux.ai/api/v1/emails/send
version=0.3.0
```

This proves the model/metadata outputs, not a published ZIP or live MailWizz picker. Existing CI runs this suite on PHP8.0 and8.3. Raw local command receipts: MAIN `.claude/artifacts/rebrand-qubrics-docs75/baseline-tests.log`, `label-tests.log`, `label-readback.log`.

Rollback source: revert the merge preserving unrelated main changes. Publication remains held: before tag/release, prepare exact next version, correlated metadata/changelog, release ZIP and prior-release rollback for Ops ASK. After approved publication, verify published asset and actual picker before docs75 consumes its labels.

Polish pass: skipped — exact technical UI-label replacements only; no new reader prose claim.

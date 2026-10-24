# Project status

Updated for the verified owner-signed release package on 2026-10-25. A version number alone does not identify a build.

| Snapshot | State |
| --- | --- |
| Public GitHub release | Stable 3.0.2; matching minified owner-signed CRX and ZIP, separate SHA-256 and per-file provenance |
| Local checkout | Accepted 3.0.2 source and minified runtime; owner CRX signer and all 98 payload files verified |
| Private GitHub `main` source | Manifest 3.0.0 at the last check; a documentation update does not synchronize runtime source |
| Chrome Web Store | Owner reported that the signed upload was accepted. Store review/publication and a listing URL have not been independently verified |

## Previous release 3.0.1

- Compact ordered folder levels and custom templates, one Booru family folder-name setting, and verified uploader/date metadata for supported Danbooru/Moebooru posts.
- Explicit access recovery for a stored destination; discarding a destination change checks the saved folder again.
- Metadata-based filenames omit the CDN basename; selected unavailable fields are skipped. Folder dates may use operation start time when publication time is unavailable.
- RedGIFs image handling and late replies from closed tabs fixed. Popup corners and Russian debug-level layout corrected; the red error stripe removed.
- File-manager reveal, picker workarounds and companion removed. Chosen-folder saving, retained-file export recovery and local media preview remain.
- Dedicated GIF encoder Worker retained from 3.0.0. No claim that large GIFs consume no time or resources.

The [3.0.1 release](https://github.com/xhthc/MediaLatch/releases/tag/v3.0.1) identifies its own artifact and tests. Its preview cache remains 128 thumbnails and 16 originals, 64 MiB per original / 128 MiB total / 24-hour availability.

## Release 3.0.2

- Manual JSON export/restore for statistics and terminal download history under Overview → Local data and backups.
- Statistics restore replaces counters, preserves the recording preference and excludes pre-restore replays. Active work prevents restore. History restore adds missing metadata-only records without fetch/retry/filesystem authority or statistics updates.
- Up to 2,048 thumbnails; 256 original previews, 128 MiB per file / 512 MiB total / 30-day availability. Cache failure or eviction does not change saved files.
- Initial window of 100 finished rows with active/focused records and selected posts kept whole. Search and bulk actions use the full retained list; producer order is preserved.
- No new permissions or dependencies; existing IndexedDB stores and download backend identities remain.
- Bound inline controls to their own post/action bar; fix Instagram photo Copy, X/Instagram focus and VK/RedGIFs account extraction. Inline request feedback distinguishes processing, transport failure and stale-page recovery from the final manager outcome.
- Composed album names preserve post position. Retire active Scatbooru domain routing while keeping historical IDs and counters.
- Reject non-string history IDs before import, preventing malformed JSON from creating duplicate or unremovable records.

The [3.0.2 release](https://github.com/xhthc/MediaLatch/releases/tag/v3.0.2) includes these changes. The owner-signed CRX retains the registered signing identity and matches every file in the verified runtime ZIP. GitHub publication and Chrome Web Store review/approval remain separate. See [local-data behavior](LOCAL_DATA.md) and [release changes](../CHANGELOG.md).

## Evidence and remaining acceptance

The combined 3.0.2 source gate passed 107/107 checks. The minified runtime passed 54 syntax checks, 13 semantic suites and the history-import regression. The extracted ZIP passed 14/14 native HTTP cases, GIF byte parity/cancellation/timeout/Worker cleanup, and actual English/Russian popup/manager rendering. Independent source and exact-package reviews approved the candidate. These are isolated fixture results, not live-site acceptance.

The local storage candidate received independent review, 1,580/1,580 UI assertions, 474/474 controller/UX checks, build parity and isolated installed-Chromium JSON/restart checks. Controlled fixtures retained 320 history records and original previews across browser restart. These counts describe that candidate, not every browser or website.

Still open: actual Reload through the user's extension-management page and folder grants, full browser restart during an active native export, uncertain chosen-folder close, pending statistics during full browser restart, physical storage pressure, signed-in site/layout coverage and device-specific viewer behavior. The auxiliary command-line `runtime.reload` experiment did not complete and is not accepted proof.

The live Reddit missing-button case and original RedGIFs Trending no-op have not been conclusively reproduced or accepted on the owner's sites. Controlled binding, feedback and recovery checks do not close those manual scenarios. Use the current task's manual-check packet and report the exact post URL, one-click time, visible outcome and redacted diagnostic journal.

## Next work

First close the bounded MV3/storage acceptance gaps. Then take selected DOM/metadata or provider problems with reproducible evidence. Stream adapters and SPA changes remain separate tasks. [Roadmap](ROADMAP.md) records scope; it does not assign implementation automatically.

Exact local candidates, owners, raw checks and handoffs remain in the ignored coordination records. Older changelog entries and screenshot captures retain their historical meaning. The current [LICENSE](../LICENSE) and third-party notices are unchanged; earlier GPL recipients retain their existing rights.

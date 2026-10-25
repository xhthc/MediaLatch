# Project status

Updated for the verified owner-signed release package on 2026-10-25. A version number alone does not identify a build.

| Snapshot | State |
| --- | --- |
| Public GitHub release | Stable 3.0.3; matching minified owner-signed CRX and ZIP, separate SHA-256 and per-file provenance |
| Local checkout | Accepted 3.0.3 source and minified runtime; owner CRX signer and all 98 payload files verified |
| Private GitHub `main` source | Not synchronized by this public release update; public tags identify documentation/release entries, not private source history |
| Chrome Web Store | [Listing supplied by owner](https://chromewebstore.google.com/detail/medialatch/cimghidldpjhhhngdhigddjfpcofhbmh). Owner handles upload; the listed version and 3.0.3 review/publication have not been independently verified |

## Release 3.0.3

- Simple folder controls and the advanced interactive path share a draft, reorderable levels and a common names/template editor. Type-folder defaults are Image/Videos/GIF; custom names and existing files are preserved.
- Compact popup search/filter row; wider debug search; separate release-version selection and New/Fixes panels. Saving and link-preview edits use sticky Save/Discard actions. Existing allowed preview domains are retained.
- Page notices offer 2/4/8 seconds or dismissal and a local test without downloads/history/statistics. Motion respects reduced motion; narrow theme/language controls have their own row.
- Completed browser-owned downloads can request Show file in folder after native-ID, ownership and existence checks. Chosen-directory exports explain the file-manager API limitation; imported history grants no file access. No companion is included.
- An uncertain export can recheck the exact owned saved result without refetching/overwriting, correcting the same history/statistics operation only after proof.
- Pending statistics can recover across full browser restarts with deduplication and clear/opt-out fences. Recovery remains bounded to 200 pending contributions and available storage.
- Selected Reddit players declaring GIF can classify their MP4 for both inline/context-menu conversion, subject to existing duration/size budgets. Ordinary video remains video.
- Inline reinjection guards, bounded Instagram scans and truthful clipboard feedback. No new permissions or dependencies.

The [3.0.3 release](https://github.com/xhthc/MediaLatch/releases/tag/v3.0.3) contains verified minified CRX/ZIP files, separate SHA-256 files and per-file provenance. The CRX retains the registered signer and extension ID; all 98 files match the accepted runtime ZIP. Store publication is separate.

## Previous release 3.0.1

- Compact ordered folder levels and custom templates, one Booru family folder-name setting, and verified uploader/date metadata for supported Danbooru/Moebooru posts.
- Explicit access recovery for a stored destination; discarding a destination change checks the saved folder again.
- Metadata-based filenames omit the CDN basename; selected unavailable fields are skipped. Folder dates may use operation start time when publication time is unavailable.
- RedGIFs image handling and late replies from closed tabs fixed. Popup corners and Russian debug-level layout corrected; the red error stripe removed.
- File-manager reveal, picker workarounds and companion removed. Chosen-folder saving, retained-file export recovery and local media preview remain.
- Dedicated GIF encoder Worker retained from 3.0.0. No claim that large GIFs consume no time or resources.

The [3.0.1 release](https://github.com/xhthc/MediaLatch/releases/tag/v3.0.1) identifies its own artifact and tests. Its preview cache remains 128 thumbnails and 16 originals, 64 MiB per original / 128 MiB total / 24-hour availability.

## Release 3.0.2

- Rebuild 2026-10-25 fixes confirmed GitHub rate-limit waits across tabs/reloads, concurrent cooldown writes, ordinary HTTP 403 classification and localized retry-time controls. Manual checks and channel changes respect the server wait. The version stays 3.0.2; existing 3.0.2 installations do not detect this rebuild as newer.
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

For 3.0.3, the frozen source received independent APPROVE and 108/108 resolved code/UI gates (raw105/108 with three environment-only reruns), plus 1,683/1,683 UI assertions, 40 native source motion/layout cases and four resize/draft cases. The minified runtime retains 54 syntax checks, 13 semantic suites, 14 native HTTP cases, GIF Worker byte/cleanup checks and separate native UI/resize fixtures. Fresh release verification confirms the registered CRX signature, all 352 source pins and all 98 CRX/ZIP/runtime files. These controlled results do not establish every live site or physical device.

The original 3.0.2 package passed 107/107 source checks and 14/14 extracted-ZIP native HTTP cases, plus GIF Worker and English/Russian popup/manager fixtures. These are retained results for that earlier package.

For the 2026-10-25 updater fix, the source-code baseline passed 106/106 core/UI checks before the release-note-only delta. The final release notes/build passed 32/32 focused updater checks, typecheck, build and generated-output parity. The exact new minified package passed 54 syntax checks, 13 semantic suites, the minifier contract and the real minified history-import handler regression. Its extracted ZIP passed actual Chromium updater checks in English/Russian at 1280/390px: concurrent WebLocks writes retain the longest wait, reload preserves it, expiry sends no automatic request, and a manual check recovers successfully. Independent source and exact-package reviews approved the rebuild; all 98 owner-CRX/ZIP files match and the registered signature verifies. These controlled updater fixtures do not repeat full live-site/media acquisition acceptance. That updater-only build did not address narrow headers; 3.0.3 has separate isolated native layout coverage.

The local storage candidate received independent review, 1,580/1,580 UI assertions, 474/474 controller/UX checks, build parity and isolated installed-Chromium JSON/restart checks. Controlled fixtures retained 320 history records and original previews across browser restart. These counts describe that candidate, not every browser or website.

Isolated fixtures now cover actual extension-manager Reload with a registered OPFS handle, full browser restart during native export, an uncertain chosen-directory close and pending-statistics replay. These are separate from a Windows external-folder picker grant. The owner reports the first external-folder/Reload manual item works; its installed package identity was not independently established. Wider signed-in site/layout checks, physical storage pressure and device-specific viewer/FPS behavior remain pending.

Current Reddit/RedGIFs feed layouts, first-click behavior and actual audio/format results still require bounded live acceptance. Earlier owner spot checks and controlled binding/feedback tests do not establish all pages. Report the exact URL, single-click time, visible outcome and redacted diagnostic journal.

## Next work

Finish real-folder and wider live-site acceptance, then take selected DOM/metadata/provider problems with reproducible evidence. Stream adapters and physical storage tests remain separate tasks. [Roadmap](ROADMAP.md) records scope; it does not assign implementation automatically.

Exact local candidates, owners, raw checks and handoffs remain in the ignored coordination records. Older changelog entries and screenshot captures retain their historical meaning. The current [LICENSE](../LICENSE) and third-party notices are unchanged; earlier GPL recipients retain their existing rights.


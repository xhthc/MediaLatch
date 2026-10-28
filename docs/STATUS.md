# Project status

Latest stable GitHub distribution: **3.0.6**, with verified owner-signed minified CRX and matching runtime ZIP. Chrome Web Store submission, review and approval remain separate owner actions; GitHub publication does not establish Store status.

Updated 2026-10-29. Runtime uses private source commit `cf4ee9158378c32b811482ded104de14b05c0370`, build `534f345512e8`. Later documentation-only commits do not change that runtime identity. The release provenance records the exact source map, all 104 shipped files and separate CRX/ZIP hashes.

| Snapshot | State |
| --- | --- |
| Public GitHub release | Stable 3.0.6, verified registered RSA signer and 104/104 payload files |
| Development source | Readable 3.0.6 source; runtime minified only in the separate build project |
| Private GitHub `main` source | Full source/history synchronized for 3.0.6; public GitHub contains documentation and packaged runtimes only |
| Chrome Web Store | Public listing is linked in README. Owner handles submission; 3.0.6 dashboard review/approval/publication are not verified here |

## Published 3.0.6

Recent Downloads grows with visible media up to the bottom of the left statistics column, then scrolls internally. Collapsed groups shrink the panel; short lists allow page scrolling. Cleared or unavailable statistics retain usable bounded history. Observer-driven cap updates are coalesced into the next frame, identical writes are skipped and pending work is cancelled on hide/unmount. Native error-event collection reproduced five ResizeObserver warnings before this fix and none afterward.

Inline fixes cover Instagram Reels action rails, the TikTok profile-modal Copy/Save pair, Tumblr's current share glyph and source-post binding, Twitch clips hover ownership, and e-shuushuu /large/ renditions plus API-failure recovery. VK photo feedback retains the proven source-post link. Refused inline requests now explicitly report refusal without fake Downloads admission. Selected-post/frame/source checks remain authoritative.

Retry of a completed EXPORT_UNCERTAIN result uses the same saved-file confirmation barrier as Check saved file, without refetching, overwriting or bypassing a refusal. Byte-mismatch and queued-confirmation regressions cover this path. Eight Booru candidate cases were extracted at their original awaited position without changing behavior.

Resource work skips irrelevant Reel-pair searches on ordinary Instagram feeds, stops stale-speed timers for hidden Downloads panels/documents and writes only new/replaced preview rows. Matching synthetic 200-post/600-replacement/30-navigation profiles reduced median Instagram scan time 29.6→8.1ms with stable controls/observers. Retained JS heap stayed near 2.1MB; this is not a demonstrated whole-browser RAM, battery or live-feed improvement. Preview ownership, transactional eviction/cancellation and recovery remain unchanged.

Narrow navigation reveals the selected tab, the contextual Save bar reveals a covered edited field without changing focus/draft, reduced-motion progress has no width tween and Debug badges retain readable text. No new runtime permissions, dependencies, provider capabilities or filename/date semantics were added.

## 3.0.6 validation and limits

The final corrected source core/UI gate passed 115/115 with 1934 UI assertions. An earlier broader 3.0.6 candidate passed 116/116 including native HTTP; the final UI-only fix did not change backend bytes. The interrupted attempt before the final gate is preserved and is not counted as a pass.

The exact corrected minified ZIP passed 104 file hashes, 57 syntax checks, 13 semantic suites, native GIF decode/Worker cleanup/cancel/timeout, 81 motion cases, 41 Saving/JSON cases, 31 Recent Downloads cases with zero browser errors, 8 observer visibility cycles and 14 HTTP cases. Independent Claude Opus source/delta/artifact reviews passed; the artifact's pending-check conditions were closed by the final native evidence. The returned CRX has the registered RSA signature and matches every one of the 104 ZIP files.

These are component/source and disposable installed-browser fixtures. They do not establish every authenticated live site, native menu GUI, external Windows folder grant, full disk, assistive technology, device power use or messenger playback. Folder-date fallback is intentional; one RedGIFs cold-placement observation remains unconfirmed. Third-party Embed services may be unavailable. Existing 3.0.5 and older packages/licences remain preserved.

## Previous release 3.0.5

- Saving uses one resolved output example, split destination/subfolder controls, rectangular ordered tokens, a recessed author-platform grid, compact naming facts and direct JSON transfer actions. Save/Discard, folder permissions and explicit import Apply retain their contracts.
- Inactive choices reveal a translucent check on hover/focus with no idle icon gutter; selected order tokens retain their numbers. Desktop navigation has a theme-colored leading accent and an independent keyboard focus outline.
- Button, section, menu and popup motion respects reduced motion. Keyboard section changes suppress entry animations without reviving their first frame after focus leaves.
- First directly opened YouTube Shorts exclude related-video links from the owning ID and preserve fail-closed ambiguity checks. Instagram/TikTok discovery avoids redundant scans, Instagram rejects comment-only rails, TikTok naming uses the selected-item ID, and Gelbooru recognizes plain Original links without weakening source checks.
- No new runtime permissions or dependencies. Development-only undici maintenance is excluded from the package.

The source gate completed 115/116 checks; the UI suite passed 1,892/1,897 with five stale label/markup assertions. Those five were corrected and passed in a focused rerun; final types, UX and generated-output checks passed. This is not an uninterrupted 116/116 result. The exact extracted minified ZIP passed 57 syntax checks, 13 semantic suites, GIF lifecycle, 81 motion cases, 41 Saving/choice/JSON cases, 10 navigation cases, keyboard departure and 14 installed-extension HTTP cases. These fixtures do not establish every live site, an external OS folder grant or assistive-technology acceptance.

The [3.0.5 release](https://github.com/xhthc/MediaLatch/releases/tag/v3.0.5) includes matching signed CRX and ZIP packages, separate checksums and per-file provenance. [Folder controls](FOLDER_TEMPLATES.md) describe the updated interface.

## Previous release 3.0.4

- Add the Red theme, with theme-colored card highlights, section transitions and a background ribbon across themes. Reduced motion and hidden tabs are respected.
- Compact Link previews: 12 settings in two equal groups, source domains and local conversion of a pasted link without requesting its page.
- Copy post links on Reddit, Pixiv, Bluesky, Threads, Twitch, Tumblr and Bilibili using the selected preview domain. Bluesky, Threads and the main Tumblr feed use their own post action bars; Pixiv Copy sits beside Download.
- Synchronize paired inline controls through one reveal lifecycle. Preserve persistent post actions, keyboard navigation, text-only Reddit Copy and exact selected-media ownership.
- Hide inline controls in fullscreen while existing downloads continue. Recognize localized Bilibili URLs and keep Pixiv controls bound to the correct artwork during scrolling.
- Keep VK controls clear of the gallery counter. Compact download errors/details and remove redundant permanent Save settings buttons.
- Make selected toggles visible, prevent transient extra checkmarks and improve disclosure headers, theme menus and panel alignment.
- No new permissions or dependencies. New Copy controls do not add download adapters; embed playback depends on the external service and messenger.

The [3.0.4 release](https://github.com/xhthc/MediaLatch/releases/tag/v3.0.4) contains matching 103-file minified CRX/ZIP packages. The existing registered signing identity, licences and earlier GPL rights are preserved.

## Previous release 3.0.3

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

For 3.0.4, the final combined core gate passed108/108; later narrow review corrections passed affected Copy 69 and native Pixiv8/Reddit4 cases. UI assertions passed 1,872/1,872 separately after a wrapper timeout. The final extracted minified ZIP passed 56 syntax checks, 13semantic suites, Copy69/Pixiv44/Reddit187/Embed 210 checks,24 native pair cases and14installed-extension HTTP cases. Independent source/package reviews approved the candidate, and all 362 source pins and 103 CRX/ZIP/runtime files were verified.

Native provider-shaped fixtures are separate from live signed-in site acceptance. The owner reports working service checks. Retained GIF Worker/UI/header evidence applies to byte-identical files; a cold-run video-sampling mismatch and a passing unchanged rerun remain recorded, so deterministic video sampling is not established. Store upload is owner-reported, not proof of store approval.

For 3.0.3, the frozen source received independent APPROVE and 108/108 resolved code/UI gates (raw105/108 with three environment-only reruns), plus 1,683/1,683 UI assertions, 40 native source motion/layout cases and four resize/draft cases. The minified runtime retains 54 syntax checks, 13 semantic suites, 14 native HTTP cases, GIF Worker byte/cleanup checks and separate native UI/resize fixtures. Fresh release verification confirms the registered CRX signature, all 352 source pins and all 98 CRX/ZIP/runtime files. These controlled results do not establish every live site or physical device.

The original 3.0.2 package passed 107/107 source checks and 14/14 extracted-ZIP native HTTP cases, plus GIF Worker and English/Russian popup/manager fixtures. These are retained results for that earlier package.

For the 2026-10-25 updater fix, the source-code baseline passed 106/106 core/UI checks before the release-note-only delta. The final release notes/build passed 32/32 focused updater checks, typecheck, build and generated-output parity. The exact new minified package passed 54 syntax checks, 13 semantic suites, the minifier contract and the real minified history-import handler regression. Its extracted ZIP passed actual Chromium updater checks in English/Russian at 1280/390px: concurrent WebLocks writes retain the longest wait, reload preserves it, expiry sends no automatic request, and a manual check recovers successfully. Independent source and exact-package reviews approved the rebuild; all 98 owner-CRX/ZIP files match and the registered signature verifies. These controlled updater fixtures do not repeat full live-site/media acquisition acceptance. That updater-only build did not address narrow headers; 3.0.3 has separate isolated native layout coverage.

The local storage candidate received independent review, 1,580/1,580 UI assertions, 474/474 controller/UX checks, build parity and isolated installed-Chromium JSON/restart checks. Controlled fixtures retained 320 history records and original previews across browser restart. These counts describe that candidate, not every browser or website.

Isolated fixtures now cover actual extension-manager Reload with a registered OPFS handle, full browser restart during native export, an uncertain chosen-directory close and pending-statistics replay. These are separate from a Windows external-folder picker grant. The owner reports the first external-folder/Reload manual item works; its installed package identity was not independently established. Wider signed-in site/layout checks, physical storage pressure and device-specific viewer/FPS behavior remain pending.

Current Reddit/RedGIFs feed layouts, first-click behavior and actual audio/format results still require bounded live acceptance. Earlier owner spot checks and controlled binding/feedback tests do not establish all pages. Report the exact URL, single-click time, visible outcome and redacted diagnostic journal.

## Next work

Finish real-folder and wider live-site acceptance, then take selected DOM/metadata/provider problems with reproducible evidence. Stream adapters and physical storage tests remain separate tasks. [Roadmap](ROADMAP.md) records scope; it does not assign implementation automatically.

Exact local candidates, owners, raw checks and handoffs remain in the ignored coordination records. Older changelog entries and screenshot captures retain their historical meaning. The current [LICENSE](../LICENSE) is unchanged, and the combined third-party notices reflect the shipped components without changing their licences. Earlier GPL recipients retain their existing rights.


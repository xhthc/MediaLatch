# Project status

Latest stable GitHub distribution: **3.0.7**, with verified owner-signed minified CRX and matching runtime ZIP. Updated 2026-10-31. The owner supplied a Chrome Web Store rejection for draft 3.0.7 on 2026-10-31: Yellow Argon, excessive site keywords in the English and Russian descriptions. Revised listing copy removes those lists; resubmission and approval remain separate owner actions.

Runtime source commit: `6a82cc4b953d323d0a37a19c9d4bf547109cd5c2`, minified build `de3c1c3bbc27`, 112 runtime files. Documentation-only commits do not change this runtime identity. Each release asset has its own hash; the provenance includes the source map and every shipped file.

| Snapshot | State |
| --- | --- |
| Public GitHub release | Stable 3.0.7; registered RSA signer and 112/112 payload files verified |
| Development source | Readable 3.0.7 with matching cloud and UI changes; minification stays outside the source checkout |
| Private GitHub main | Accepted source and documentation synchronized; public GitHub contains docs and runtime packages |
| Chrome Web Store | Draft 3.0.7 rejected on 2026-10-31 (Yellow Argon); revised descriptions prepared, resubmission pending |

## Published 3.0.7

- Save to this PC, Google Drive or Yandex Disk. Connect with OAuth or a validated access token. Uploads go directly to the provider with account/application-pinned private receipts; an unavailable cloud never silently falls back to PC.
- Each destination retains its subfolder, folder layout and filename policy. Universal setup fills all three profiles while preserving subfolders and labels. Existing files are not moved or renamed.
- Ordinary inline Download remains local. Selecting a cloud reveals adjacent selected/all cloud actions; choosing This PC hides those actions without disconnecting accounts. Galleries use a shared neutral dock, and popup/context-menu saves keep the chosen global destination.
- Cloud space is shown below left navigation in every section. Provider capacity uses 1024 steps; saved-file volumes retain decimal units. Yandex email is optional during sign-in; Disk information uses a separate optional consent action.
- Filename rules can apply to all services or a selection and use download start or known publication dates. A save captures its destination/policy once. Narrow thumbnail ownership queries avoid rebuilding full history.
- Shared motion respects reduced motion; the popup Settings, Pause and Trash drawings stay stationary. Add the identity permission for cloud sign-in; no new host permissions or dependencies.

Setup and limits: [Cloud destinations](CLOUD.md), [Russian setup](CLOUD.ru.md), [folder/name profiles](FOLDER_TEMPLATES.md), [privacy](PRIVACY.md).

## 3.0.7 validation and limits

The final source core/UI/native gate passed 133/133. The minified runtime passed 65 JS/MJS syntax checks, 13 semantic suites and 7 additional cloud/profile suites. Source-format-dependent checks were adapted only for minified function boundaries and translated catalogue access; the unshipped source-configuration CLI was covered by the full source gate. Independent source and artifact reviews resolved the release-note category mismatch and found no remaining blockers.

The exact extracted ZIP passed real offscreen GIF decode/Worker cleanup/cancel/timeout, four localized manager/popup pages, 14 native HTTP/cache/Range cases, seven cloud-flow cases with 20 layouts, 58 capacity cases and 40 static-toolbar icon cases. Automated provider responses were local fixtures; they are not real-account OAuth or quota acceptance. The owner separately reports local testing; screenshots show both connected accounts and capacity, plus one X image in the expected Yandex folder.

Still separate: final Store OAuth/branding, real quota/revocation edge cases, all authenticated sites, external OS folder grants, full disk and messenger Embed playback. Historical performance samples are synthetic workloads, not whole-browser RAM or battery measurements. Previous packages, tags, licences and GPL rights are preserved.

Notice metadata check on 2026-10-31: all 59 UI dependency entries match installed versions and full licence texts; source and minified notice files match. The root notice's historical `gifenc.js` SHA-256 does not identify the current source or minified file. The MIT text is retained; that stale checksum remains a known documentation limitation in the signed 3.0.7 package. Release checksums and per-file provenance identify the actual shipped bytes.

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

## Published 3.0.5

- Saving uses one resolved output example, split destination/subfolder controls, rectangular ordered tokens, a recessed author-platform grid, compact naming facts and direct JSON transfer actions. Save/Discard, folder permissions and explicit import Apply retain their contracts.
- Inactive choices reveal a translucent check on hover/focus with no idle icon gutter; selected order tokens retain their numbers. Desktop navigation has a theme-colored leading accent and an independent keyboard focus outline.
- Button, section, menu and popup motion respects reduced motion. Keyboard section changes suppress entry animations without reviving their first frame after focus leaves.
- First directly opened YouTube Shorts exclude related-video links from the owning ID and preserve fail-closed ambiguity checks. Instagram/TikTok discovery avoids redundant scans, Instagram rejects comment-only rails, TikTok naming uses the selected-item ID, and Gelbooru recognizes plain Original links without weakening source checks.
- No new runtime permissions or dependencies. Development-only undici maintenance is excluded from the package.

The source gate completed 115/116 checks; the UI suite passed 1,892/1,897 with five stale label/markup assertions. Those five were corrected and passed in a focused rerun; final types, UX and generated-output checks passed. This is not an uninterrupted 116/116 result. The exact extracted minified ZIP passed 57 syntax checks, 13 semantic suites, GIF lifecycle, 81 motion cases, 41 Saving/choice/JSON cases, 10 navigation cases, keyboard departure and 14 installed-extension HTTP cases. These fixtures do not establish every live site, an external OS folder grant or assistive-technology acceptance.

## Published 3.0.2 (rebuilt)

- Manual JSON export/restore for statistics and terminal download history under Overview → Local data and backups. Statistics restore replaces counters, preserves the recording preference and excludes pre-restore replays; active work prevents restore. History restore adds missing metadata-only records without fetch, retry, filesystem authority or statistics updates.
- Preview cache of up to 2,048 thumbnails and 256 original previews (128 MiB per file / 512 MiB total / 30-day availability); eviction or failure never changes saved files.
- Initial window of 100 finished download rows with active/focused records and selected posts kept whole; search and bulk actions use the full retained list.
- Inline controls bound to their own post/action bar; Instagram photo Copy, X/Instagram keyboard focus and VK/RedGIFs account extraction fixed; inline request feedback separates processing, transport failure and stale-page recovery from the manager outcome.
- Composed album names keep post position (`_001`, `_002`); Scatbooru domain routing retired while historical IDs and counters stay; non-string history IDs rejected before import.
- Update checks distinguish ordinary HTTP 403 from a confirmed GitHub rate limit, keep the server cooldown across pages and reloads (longest wait wins under Web Locks) and show the next permitted check time.
- No new permissions or dependencies; existing IndexedDB stores and download backend identities remain.

Published 3.0.1 and earlier changes keep their historical meaning in the [changelog](../CHANGELOG.md): ordered folder levels and custom templates, the Booru family folder name, explicit folder-access recovery, metadata-based filenames, RedGIFs image handling and the removal of the Explorer/companion helper. See [local-data behavior](LOCAL_DATA.md) and [folder templates](FOLDER_TEMPLATES.md).

## Published 3.0.3

The Updates history uses category panels matching the supplied reference: new items and notes on the left, one fixes panel spanning their height on the right, shared header filters and 24/16 px outer/inner spacing on wide layouts. Motion polish keeps chip gradients present through both selection directions, gives folder checks interruptible transitions and adds a measured navigation indicator. Native disclosures use intrinsic-height transitions only where supported; reduced motion and keyboard navigation keep immediate state changes. Download-history rows do not replay a global entrance when filtering or scrolling.

- **Settings and compact surfaces.** Simple folder controls and an advanced interactive path share one draft; advanced levels move by drag or keyboard, retain literal/combined levels and open a common names/template editor. Dirty Saving/Link previews use one sticky Save/Discard bar. Link previews retain allowed domains and independent YouTube video/Shorts choices; cards have their own height and service hints. Popup search/types share the compact row again. Debug retains the square grouping checkbox and a wide search field. Updates has separate version selection, adjacent arrows and All/New/Fixes categories; manual instructions collapse unless a newer release exists. No autosave or new mirror domain is introduced.
- **Notification controls.** A validated immediate preference selects 2/4/8 seconds or until dismissed for new terminal page notices; hover/focus pauses timed cards. A local test in settings uses the actual renderer, selected theme/corner and duration without a synthetic operation, history or statistics entry. Portable settings carry the preference.
- **File location.** Completed browser-owned downloads can request Show file in folder after an exact-ID/existence/extension-ownership check. Chosen-directory exports show an information icon explaining the File System Access limitation; this does not claim writing is denied. Location follows the actual retained job, not today's destination. Imports have no native ID or folder authority. No companion, custom-directory Explorer link or new permission is added. The Chrome show API returns no visibility acknowledgement; actual OS opening remains manual acceptance.

- **Uncertain export recovery.** Check saved file rechecks the exact owned native result or chosen-directory bytes. Blank, changed or still uncertain results refuse; a confirmed result corrects the same operation in feedback/history/statistics, including after session loss, without a second transfer or overwrite. Clear/restore boundaries still apply.
- **Reddit GIF players.** A connected selected player declaring `gif` with the matching post ID can classify its exact Reddit MP4 as an animation for both inline and context-menu saving. Posters, changed declarations and other posts do not supply proof. The shared 30-second/input/output budgets still decide GIF versus an explicitly explained MP4 fallback.
- **Media type folder names.** Defaults for new saves are `Image`, `Videos` and `GIF`; internal type IDs remain `pic`, `video` and `gif`. Independent single-segment replacements affect the `{type}` level only, through the same resolver and site-name pattern; `unknown-type` is never renamed. Explicit saved names, admitted paths and existing files stay unchanged. Validated in the browser path, the chosen-folder path and both animation outputs, in portable settings and in the import preview. Details: [folder templates](FOLDER_TEMPLATES.md).
- **Narrow FullApp header.** At phone widths the theme and language controls take their own row instead of covering the brand. Measured with real rectangles at 320/390/1280 px, RU/EN, four themes; a pre-fix build fails the same check.
- **Statistics recovery.** Failed counter writes keep compact private pending contributions across full browser restarts, without URLs, file names or arbitrary browsing hosts. The ledger prevents duplicate counts; opt-out and clear/restore fences remain authoritative. Both-store failure or a full 200-item pending queue remains a bounded recovery limit.
- **Clipboard feedback.** All inline copy controls and source-page notices distinguish a proven write, an unconfirmed fallback and a refusal. No clipboard-read permission is added.
- **SPA reinjection.** X, TikTok and YouTube reuse their initialized script; Instagram already did. A synthetic browser profile of X (200 cards, 600 replacements, six reinjections) changed from 2→8 observers/158 scans to 2→2 observers/60 scans, with no idle scan loop; this is not a live-site timing claim.
- **Measured discovery.** On the same synthetic workload, Instagram's median scan fell from about 284 to 27 ms after bounding ambiguity checks and skipping reconciled rails. X with actual history navigation and YouTube also retain two observers and no idle loop. These synthetic page measurements do not establish installed-extension or live-site timings.
- **Native diagnostic cases** in `tools/diagnostics/mv3-storage-acceptance.cjs` (`p1-*`), see the section below.

This section describes release 3.0.3. The additional 3.0.4 changes follow.

## Published 3.0.4

- Red theme, matching toolbar icons and theme-aware page motion across all seven sections; hidden tabs and reduced motion suppress unnecessary animation.
- Compact Link previews groups, source/result tester and seven added platforms. On-site Copy uses the same saved preview preferences; no new download adapters or clipboard-read permission.
- Persistent native post actions on Bluesky, Threads and the Tumblr feed. Pixiv Copy is adjacent to its proven Save rail, with keyboard traversal and immediate stale-rail removal during scroll rearming. Bilibili locale paths and main-player ownership are checked before recommendation ancestors.
- Paired inline controls synchronize through one reveal lifecycle while preserving persistent post actions, keyboard navigation and exact selected-media ownership.
- Universal fullscreen visibility/action protection for inline controls; admitted downloads remain independent. Selected chips no longer flash unchecked checkmarks during section transitions.
- Shared disclosure headers, clearer selected states, compact error/details panels, VK gallery-counter clearance and one Save/Discard draft bar.

The owner reports testing all services successfully with no observed bugs, while external embeds remain unstable; leave those services unchanged. This report is bounded to the owner's tests and does not guarantee every layout, mirror or messenger. Local Chromium/controller checks and independent review remain separately recorded in the release receipt. GitHub publication of the verified signed CRX/ZIP is recorded separately; the owner-reported Store upload is not proof of Store review or approval.

## Local post-release development tooling

The UI development lockfile moves jsdom's transitive `undici` from 8.11.2 to 8.12.2, the fixed bound of GHSA-xjj6-f33q-929c and two related advisories, inside jsdom's existing `^8.10.2` range. No package manifest, runtime file or dependency set changes; undici is not in the published 3.0.4 CRX/ZIP, and nothing here shows the extension was affected. Acceptance of this development-only update requires a clean install, audit and UI gate; their results are kept in local coordination evidence.

## SPA efficiency included in 3.0.5

Release 3.0.5 ports the TikTok/Instagram mutation filters onto the newer paired-control/binding/fullscreen guards. TikTok ignores unrelated DOM and own-icon feedback while retaining recycled-card cleanup, including without ResizeObserver; Instagram ignores own-icon feedback and uses one scroll capture listener. These changes first ship in 3.0.5. Acceptance, exact candidate and test/review evidence live in the coordination handoff; broader live-feed performance remains separate.

## Audit findings included in 3.0.5

The completed Claude Desktop audit is partial: real default-setting saves were observed on a subset of X, Pixiv, RedGIFs, VK/VK Video, Instagram, TikTok and E-Shuushuu cases. Other archive/Booru checks often confirmed only page/original-file reachability. Default Copy URLs and mirror HTTP responses do not prove messenger playback. The audit did not cover all native context-menu saves, internal manager/settings workflows, mirror switching or every listed site.

Source regressions reproduce stray Instagram comment Copy controls and generic TikTok video names; the 3.0.5 fixes require a native post action rail and use the verified selected TikTok item ID. The Gelbooru-family parser also recognizes plain `Original` links with its existing domain/path/hash checks. A real Realbooru context-menu save remains a separate live check. Validation and final review are bound to the exact coordination candidate, not this prose.

Tool-inactive-tab `SENDER_REJECTED` observations do not justify removing sender checks. A single unreplicated VK first-click miss, Instagram720p versus1080p observation, VK clip duration difference, and DNS/503/Cloudflare/mirror500 observations remain bounded findings rather than proven general defects or permanent domain retirement. No code or settings were changed by the Claude audit itself.

## Evidence and remaining acceptance

Shorts cold-open correction in 3.0.5: a paused renderer without native active markers
can use the current Shorts route only when its control was admitted for that same
owner/route from the document's initial Shorts address, it remains the unique mostly visible renderer and no other renderer
declares itself active. Hidden/overlapping owners
and conflicting DOM IDs remain refused. Before/after routed Chromium evidence is
separate from live-site acceptance; this change first ships in 3.0.5.

The owner-browser retest found a second cause of `NO_SHARE_URL`: the first
Short's renderer also encloses a related-video carousel link. That carousel
is excluded from owning-link evidence; other conflicting IDs still refuse.
The corrected unpacked source copied the selected first Short in the owner's
Helium using the native clipboard write path. This correction ships in 3.0.5; it does not establish third-party mirror playback.

Evidence kinds stay separate: unit/controller/jsdom checks, isolated installed-Chromium fixtures in disposable profiles, and signed-in or owner-browser acceptance. Counts describe one candidate, not every browser or website.

Isolated-browser results first recorded for the 3.0.3 source (real extension, loopback HTTP, disposable profile; the "chosen directory" is an OPFS directory registered in the extension's private storage, not an OS picker grant):

- A full browser restart while a native export was admitted and in progress: the manager marked the interrupted export failed, kept the staged bytes, and one explicit Retry produced exactly one correct output file with one source fetch and one statistics contribution.
- Chosen-directory close, killed after the bytes committed but before the receipt: exact-byte reconciliation completed the job once, with no second write and no refetch. Killed before commit: the row stays `EXPORT_UNCERTAIN`; Check saved file refuses blank/changed bytes and can accept a later exact match without writing again. Removing the row discards retained bytes and leaves the claimed target for the user.
- A failed statistics database contribution is replayed once from private durable pending storage after a full browser restart; a later genuine save adds exactly one more. The final native case requires recovery, rather than passing a known-loss observation.
- Actual Reload through `chrome://extensions` replaces the worker and retains settings, history, counters and the registered OPFS handle; a second save succeeds. This is separate from an external Windows folder grant.

Owner reports: the supplied VK Video sample downloads with sound, and other tested Reddit/RedGIFs cases work. The Reddit sample `/r/memes/s/NqQlMsk4Gn` saved `reddit.mp4` through both controls; its public embed declares GIF, which led to the fix above. Retest that sample with 3.0.3 or later; owner reports do not establish every layout, full duration or browser.

Still open and manual: real external OS picker grant/cancel/recovery across Reload, physical storage pressure, wider signed-in site/layout coverage and device-specific viewer behavior. The owner reports the first external-folder/Reload manual item works; its installed package identity was not independently established. The earlier command-line `runtime.reload` experiment remains historical failed evidence; the new manager-UI fixture is the accepted isolated Reload route.

## Next work

Close the remaining manual acceptance above, then take selected DOM/metadata or provider problems with reproducible evidence. Stream adapters and observer changes need a measurement first. [Roadmap](ROADMAP.md) records scope; it does not assign implementation automatically.

Exact local candidates, owners, raw checks and handoffs remain in the ignored coordination records. Older changelog entries and screenshot captures retain their historical meaning. The current [LICENSE](../LICENSE) and third-party notices are unchanged; earlier GPL recipients retain their existing rights.

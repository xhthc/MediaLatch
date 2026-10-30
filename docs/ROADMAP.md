# Architecture roadmap

Updated 2026-10-31 for released 3.0.7. See [status](STATUS.md) for runtime identity, measured results and acceptance limits. Publication does not assign the next task.

## Implemented foundation

| Area | Current behavior |
| --- | --- |
| Selected-media ownership | Gesture, post, frame/document and exact source proof; bounded srcset and open/closed-shadow handling; ambiguous selections refuse |
| Acquisition and recovery | Disk-backed staging, private durable jobs, retryable prepared files, native download IDs versus chosen-directory receipts, restart reconciliation and cleanup intent |
| Runtime lifetime | Owner-aware offscreen lifetime, dedicated GIF encoder Worker, cancellation/resource budgets; no global keep-alive promise |
| Organization | Ordered folder templates, site/Booru labels, proven account metadata, composed filenames without CDN tails, explicit folder-access recovery |
| History/statistics | Persistent history and opt-in all-time counters; startup retry, pending-statistics protection across worker restarts and measured transfer rate |
| Local data (published 3.0.2) | JSON backups/restore of statistics and history, larger disposable preview cache, bounded rendering with complete posts; no new permission or dependency |
| Update checks (published 3.0.2) | Persisted server cooldown, confirmed-rate-limit classification and a manual recovery path |

Do not reimplement these mechanisms from older audits. Source checks, isolated-browser fixtures, user reports and general live-site acceptance are different evidence.

## Published 3.0.7

- Direct Google Drive/Yandex Disk saves, separate destination policies, private account-bound receipts and optional OAuth/token connection.
- Shared local/cloud inline dock, selected/all gallery actions and global-destination behavior in popup/context menu.
- Persistent sidebar cloud capacity, optional Yandex capacity/email consent, universal setup across three profiles and service/date filename scope.
- Captured destination/policy and narrower thumbnail ownership lookup; stationary popup toolbar drawings and refined reduced-motion behavior.
- Verified signed minified 112-file CRX/ZIP; core/UI/native 133/133 and bounded artifact evidence in [status](STATUS.md).

Next assigned work can address real Store OAuth/branding and cloud quota/revocation, large uploads and recovery on actual accounts. Do not rebuild the implemented cloud system from older proposals.

## Published 3.0.3

- Per-media-type folder names: `Image`, `Videos` and `GIF` defaults, preserving explicit custom names and internal type IDs (see [folder templates](FOLDER_TEMPLATES.md)).
- Narrow-viewport FullApp header layout (320/390 px) with real-rectangle geometry acceptance.
- Isolated-browser cases for a full browser restart during an admitted native export, an uncertain chosen-directory close and pending statistics through a full browser restart. The statistics case requires recovery without duplicate counting.
- Actual extension-manager Reload with retained data and registered OPFS access, followed by another save; external OS picker permission remains separate.
- Check saved file for `EXPORT_UNCERTAIN`: exact owned-result reconciliation, no refetch or overwrite, and correction of the same history/statistics operation after proof.
- Explicit selected-player GIF declarations on Reddit reach the shared converter through inline and context-menu saving. Posters, foreign ownership and changed markers refuse; the existing conversion budgets remain.

- **Statistics recovery.** Failed counter writes keep compact private pending contributions across full browser restarts, without URLs, file names or arbitrary browsing hosts. The ledger prevents duplicate counts; opt-out and clear/restore fences remain authoritative. Both-store failure or a full 200-item pending queue remains a bounded recovery limit.
- **Clipboard feedback.** All inline copy controls and source-page notices distinguish a proven write, an unconfirmed fallback and a refusal. No clipboard-read permission is added.
- **SPA reinjection.** X, TikTok and YouTube reuse their initialized script; Instagram already did. A synthetic browser profile of X (200 cards, 600 replacements, six reinjections) changed from 2→8 observers/158 scans to 2→2 observers/60 scans, with no idle scan loop; this is not a live-site timing claim.

## Published 3.0.4

- Red theme and theme-aware motion; hidden tabs and reduced motion suppress unnecessary animation.
- Compact Link previews and on-site Copy on seven added platforms using the saved preview preferences; no new download adapters or clipboard-read permission.
- Persistent native post actions on Bluesky, Threads and the Tumblr feed, Pixiv Copy beside its proven Save rail, paired inline controls synchronized through one reveal lifecycle, fullscreen suppression of inline controls and VK gallery-counter clearance.

## Published 3.0.5

Unified Saving output and compact controls, indexed tokens and hover-check feedback, direct settings transfer and desktop navigation accents are implemented. Motion respects keyboard/reduced-motion controls. Shorts cold-open ownership, Instagram action rails, TikTok identity-based naming and Gelbooru Original parsing are repaired. Reuse the recorded tests; broader live-site acceptance remains open.

## Published 3.0.6

- Natural Recent Downloads height capped by the left statistics bottom, with shrink-on-collapse, real inner/page scrolling and a ResizeObserver delivery-loop fix.
- Instagram/TikTok/Tumblr/Twitch/e-shuushuu inline recovery and explicit refusal acknowledgement; proven VK source-post feedback, narrow navigation and Save-bar clearance.
- Uncertain-export Retry uses the existing confirmation barrier; byte/collision/concurrency boundaries stay intact. Booru test extraction preserves execution order.
- Measured Instagram scan reduction, suspended hidden stale-speed timers and incremental preview inserts, with no new permissions/dependencies or whole-browser memory claim.
- Corrected source 115/115 plus exact minified GIF/UI/HTTP acceptance and verified 104-file CRX/ZIP identity. Manual external-folder, broader live-site and device-performance rows remain open.

## Unreleased after 3.0.7

**Cloud destinations (implemented in source, not live-accepted).** A Storage section, a destination chooser (Storage, Saving, toolbar popup), Google Drive and Yandex Disk uploads with OAuth or an advanced access token, and the shared folder/name rules beneath an application-owned root. Owed: publisher OAuth registration (Google Chrome Extension client per Item ID, Yandex application and Redirect URI), then live acceptance of sign-in, a real upload in Chrome and Helium, quota/revocation paths and live-site local/Cloud controls. Isolated Storage locale/theme/width checks and provider HTTP fixtures passed; they are not real-cloud acceptance. Not planned for the first version: a cloud browser, shared drives, sync, several simultaneous destinations. See [CLOUD.md](CLOUD.md).

The current source cycle consolidates folder/name preference projection, preserves the captured destination throughout preparation, and removes full-history allocation from per-thumbnail ownership checks (see [status](STATUS.md)). Production-path and identity/recovery regressions accompany the changes; source/browser acceptance is recorded separately. The accepted 3.0.7 package is unchanged. Wider publication-date extraction still needs a selected-item response contract; the manager's durable whole-record writes remain unchanged. Physical folder grants, live layouts and messenger playback still need manual acceptance.

## Open sequence

The verified inline/control and narrow-UI repairs above are released and reviewed. Retest exact site layouts when their DOM changes; blocked/native-menu/messenger rows remain separate acceptance. Folder dates retain the documented UTC publication-date/accepted-job fallback; the isolated RedGIFs cold-placement observation needs reproduction before a patch.

The Claude Desktop sites audit is partial. Next acceptance must exercise real extension saves, context-menu paths and everyday manager/settings/history/statistics/Link previews workflows with a proven tool preflight. Site-original reachability is not a completed extension test. Confirmed local Instagram/TikTok/parser repairs are described in [status](STATUS.md); do not requeue their implementation after acceptance.

| Priority | Outcome | Acceptance boundary |
| --- | --- | --- |
| P1, manual | Close the external-folder evidence gap | Actual manager Reload, native export/browser restart and uncertain directory-close cases exist in isolated profiles. Verify the owner's real external OS picker grant across Reload separately; the owner reports the first manual item works, which is not a universal grant guarantee |
| P1 | Verify real destinations and storage pressure | Real external OS picker cancel/grant/recovery, retained-file retry and collisions. API quota injections are not physical full disk or natural eviction |
| P2 | Fill selected DOM/metadata gaps | Reproduce an exact failing target/overlay/frame first; bounded discovery and no page-wide first-video or nearest-large-image substitution |
| P2 | Extend original/protected providers | A named provider, exact host and selected-item proof; preserve signed URLs and scoped request rules. HEAD/MIME/size alone do not prove the original or ownership |
| P2 | Finish live interaction acceptance | Signed-in author routes, provider layout/audio checks and the new unconfirmed-clipboard feedback on actual pages. Do not claim a write when a page intercepts the native event |
| P2, broader samples | VOD on VK Video and RedGIFs | Owner confirms the supplied VK sample downloads with sound and other tested Reddit/RedGIFs cases work. Existing progressive-file support handles these reports; no new adapter is justified by them. Full-duration/audio acceptance of other items remains sample-specific |
| P3, profiling | Measure resource cost before further changes | The released Instagram optimization removes measured irrelevant Reel-pair searches; repeated matching synthetic profiles show 29.6 to 8.1 ms median scans with stable controls/observers. This is part of released 3.0.6 and separate from older profiles. Next: actual-device feeds and large-history/preview or conversion workloads if those profiles identify a bottleneck; no meaningful whole-browser RAM reduction is established |
| Separate capability | Add a scoped stream adapter | Named player/provider, playlist ownership, supported VOD/codecs/encryption/audio limits, cancellation, bounded storage and actual playback tests |

The native diagnostic already covers bounded worker/offscreen stops, restart reconciliation, full browser restarts and injected storage failures. Reuse it for missing cases (`p1-*` selects the 2026-10-25 group); do not repeat completed cases or promise universal crash recovery. [release evidence](STATUS.md) describe its limits. [Chrome's lifecycle contract](https://developer.chrome.com/docs/extensions/develop/concepts/service-workers/lifecycle) requires durable state rather than reliance on globals or periodic messages.

## Product questions not yet assigned

- Broader posting-time extraction and physical renaming of previously exported files need separate designs; do not guess dates from unrelated metadata or introduce an Explorer companion. Existing files are never renamed by a folder or filename change.
- Firefox, author archives and store automation remain separate work.

## Deferred proposals

Universal MAIN-world Blob/revoke hooks, a per-tab network sniffer and universal HLS/DASH are not implemented. A nearby request, thumbnail, `embedUrl`, `MediaSource` or successful URL rewrite does not grant authority to fetch an original. Any new network observer requires its own permission/privacy decision and selected-player proof. YouTube downloading, DRM and live streams remain unsupported.

All future work preserves current provider priority, exact signed URLs, private credentials/state, native IDs versus directory receipts, cancellation, no-overwrite behavior and truthful errors. Each packet needs production-path regression checks, independent review and separately identified browser/file evidence. Packaging, source synchronization and publication require their own authorized task.

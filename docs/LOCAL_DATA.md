# Local data and backups

Version 3.0.2 includes JSON statistics/history copies, history windowing and the larger preview cache. Portable settings export remains separate. These local features do not create an automatic external database or cloud backup.

## What persists

Download jobs and all-time statistics live in private extension IndexedDB in the browser profile. Neither has an automatic count/age expiry; available storage still limits them. Settings use extension local storage. Recent feedback is a separate session list targeting 20 terminal operations and 24 hours, with active and pending-statistics protections. Its small size does not cap the durable download history or totals.

Deleting a manager record does not delete the exported media file. Clearing statistics does not clear history or saved files. Uninstalling/removing extension storage can remove extension-local data. A copied browser profile, changed extension ID or store installation is not a promised migration mechanism.

## Cache limits

| Disposable cache | Previous 3.0.1 | Current 3.0.2 |
| --- | --- | --- |
| Static WebP thumbnails | 128 | 2,048 |
| Original previews | 16 | 256 |
| Maximum cached original | 64 MiB | 128 MiB |
| Original cache byte budget | 128 MiB | 512 MiB |
| Original availability | 24 hours | 30 days |

These limits apply to optional previews, not the maximum download size. Eviction, expiry or a cache write failure leaves the exported file and export receipt intact. Expired entries become unavailable; pruning runs during cache writes/startup, not as a promise of deletion while the browser is closed. There is no extra source request to refill an evicted original. Supported files can instead be chosen explicitly from disk. No external config file, helper or new storage permission is introduced. Browser quota/eviction still applies; a cache is not a backup. [Chrome storage behavior](https://developer.chrome.com/docs/extensions/develop/concepts/storage-and-cookies).

## Export and restore in 3.0.2

Open **Overview → Local data and backups** (Russian: **Обзор → Локальные данные и резервные копии**). Export statistics and history as two separate JSON files. Keep the history copy private: it contains names and account labels. Each file must fit 32 MiB in UTF-8; a history copy supports up to 50,000 records.

| Copy | Included | Restore behavior |
| --- | --- | --- |
| Statistics | Aggregate outcomes, output types and measured-byte counters by site | Explicit confirmation replaces every counter; it does not add to existing totals or enable recording. Finish/cancel active work first. Requests started before restoration are excluded from later counting |
| History | Terminal record IDs, basenames, site/account metadata, timestamps, outcomes and byte totals | Explicit confirmation adds only missing IDs. Existing rows remain. Repeating the same import creates no duplicates or statistics contributions |

The worker validates file format/version, counters and record limits before committing the selected store. Invalid input, including non-string history IDs, or a failed transaction keeps prior data. A failed restore keeps the selected copy available for retry; success returns focus to the file chooser.

Copies exclude media and thumbnails, source/post URLs, signed queries, request headers, native download IDs, directory handles/receipts and active downloads. They cannot restore a folder grant or unfinished transfer. Restored history rows are marked as records from a copy; they cannot retry a download or establish that the file still exists. To preview such a file, select the original file from disk when the viewer supports it.

## Long history

The interface initially selects up to 100 finished rows. Active/focused records and every file of a selected post remain visible; complete-post expansion can exceed 100 rows. Load more expands the window. Search, filters and bulk actions use the full retained history, not only the first window. This changes rendering, not retention.

## Verification limits

Validation, duplicate imports, transaction aborts, replay boundaries, recording opt-out and archive-only restart have regressions. Isolated installed-Chromium checks cover JSON downloads/file input, 320 retained records, browser restart and both interface languages/themes. Real extension-manager Reload, external OS-folder grants and physical low-disk/eviction remain manual acceptance. GitHub release and Chrome Web Store review/approval remain separate.

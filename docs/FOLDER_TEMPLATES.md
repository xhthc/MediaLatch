# Folder templates

Folder templates are available since published 3.0.1; per-media-type folder names shipped in 3.0.3 and remain in 3.0.5. See [status](STATUS.md) for release and acceptance boundaries.

Saving has one relative base subfolder and an ordered folder template. Changes remain
a draft until Save settings. The preview uses the same resolver as downloads.

In 3.0.5, one live output below the header shows the complete resolved example, with neutral root, violet subfolder, cyan levels and green filename. Destination and subfolder controls share a two-column card. Simple and Advanced share one unsaved draft. Selection order sets folder nesting; selected levels show ordinal badges from1. Inactive choices reserve no icon gutter and reveal a translucent check on hover/focus. Advanced retains literal, combined and duplicate levels, drag or Alt+Left/Right reorder, Delete/remove and the common names/template editor. One Folder clears explicit custom levels without changing author opt-ins. Author platforms use a compact responsive grid; unknown metadata stays omitted. File naming uses the same resolver. The one sticky Save/Discard bar remains explicit; direct JSON import first prepares a preview and requires Apply. Existing exported files never move when these settings change.

| Preset | Levels after the base subfolder |
| --- | --- |
| One folder (`single`) | `{author}` when enabled and known; otherwise none |
| Site / author / type (`by_site_and_type`) | `{site}/{author}/{type}` |
| Site / author | `{site}/{author}` |
| Site / type / author | `{site}/{type}/{author}` |
| Type / site / author | `{type}/{site}/{author}` |
| Month / site / author | `{month}/{site}/{author}` |
| Custom | Your validated string, including static levels |

Click tokens in the desired order, or enter a template such as
`Art/{site}/{author}` or `{type}/{year}/{site}`. Site folder names replace a single
`{site}` level per service; an empty replacement restores the canonical name.
The single **Booru** choice covers every site marked as Booru in the supported-sites
catalogue, including future additions. It affects folder labels only: actual site IDs,
filename site tokens and statistics stay individual. Existing imported per-board
replacements take precedence over the group value. The editor warns when these values
differ; changing or resetting Booru removes all per-board replacements in the draft.
The adjacent example names its representative board and uses the same resolver.

Tokens are `{site}`, `{author}`, `{type}`, `{ext}`, `{date}`, `{month}` and `{year}`.
Date/month/year use UTC and proven publication metadata when available, otherwise
the operation's fixed creation time. Retry keeps the existing path. Media type and
extension describe the actual output, including converted GIFs and MP4 fallbacks.
Unknown metadata omits its level, including static decoration in a mixed level.
There is no `unknown-author` folder. A missing proven account is not guessed from
the current page's profile.

The existing seven account switches retain their behavior. The separate Booru uploader
switch uses only matched Danbooru/Moebooru uploader metadata; artist tags are not account
identity. An unsupported board or unknown uploader skips the author level. Filename
author/date choices continue to work independently of author-folder preferences.

Templates are relative, slash-separated and reject unknown tokens, malformed braces,
empty/traversal/absolute levels, reserved names and excessive depth or size. The root
and template each permit at most 10 levels; existing deep legacy roots remain valid.
The final relative filename path is limited to
240 UTF-16 units and each name to 238 UTF-8 bytes. Only the file basename can be fitted;
chosen folder structure is never silently truncated. Combined paths that cannot fit fail
visibly rather than silently changing folders.

Portable settings include templates, presets, per-site/family replacements, media-type names and folder switches.
They exclude directory handles, local paths and download history.
Stored presets and explicit folder-name replacements keep their values. Default names for new saves are described below; existing files and admitted jobs retain their original paths.

## Filename services, dates and Universal setup

File naming uses one common field selection for all selected services. **Names apply to** can retain all services, select individual services/Booru as a family, or clear the selection to keep original names everywhere. Unselected services keep their original basename without changing folder organization. Other sites covers owners without a separate catalogue entry. Folder-label replacements do not change a site's filename identity.

With Date enabled, **Download start date** uses the operation's existing creation time on any service; **Publication date (when available)** uses only confirmed X or supported Booru post metadata. Missing dates/authors are omitted. UTC date/time, album indices, output extensions, portable name limits and collision handling remain in effect. Existing preferences keep publication-date behavior until changed; no additional post-metadata request is introduced for this feature. Authors remain the proven selected accounts on supported services, or the existing supported Booru uploader; other unknown authors are omitted.

**Saving profiles.** This PC, Google Drive and Yandex Disk retain separate subfolders, layout, label overrides, author choices and filename rules. Selecting a destination changes the profile being edited; unsaved drafts survive switching. The PC profile retains its existing top-level storage keys. Missing cloud profiles inherit the legacy PC policy until the first policy save seeds them separately. Save applies all dirty profiles; Discard restores all of them. An admitted operation uses the policy of its captured destination.

**Universal setup** fills all three profile drafts with site / author / media-type folders, supported author-folder options and date/time/site/author filename fields for all services, using download-start dates. Each root/subfolder, folder-label overrides, the destination and unrelated preferences stay unchanged. No existing file is renamed or moved and no folder is created by pressing the preset button. Portable settings JSON carries the profiles and scope/date preferences; directory grants, accounts and credentials do not travel with it. Older JSON backups remain supported.

## Media-type names and existing files

The `{type}` level uses `Image`, `Videos` and `GIF` by default for the internal `pic`, `video` and `gif` categories; non-media or unprovable output uses `unknown-type`. Settings → Saving → **Media type folder names** renames the first three independently. An empty field uses the same default shown by its placeholder. Explicit saved names, including `pic`, `vid` or `gif`, remain custom choices; reset them and Save to use the new defaults. `unknown-type` has no setting. A label replaces only the `{type}` token; a static level such as `Images` in a custom template stays literal for every type, and Site/Booru replacements still change only `{site}`.

A label is one folder name of at most 50 characters. It cannot contain `/`, `\` or control characters, be `.`/`..` or a reserved device name, or begin or end with a space or dot. An invalid draft is flagged beside its field and in the example path, and Save refuses it (storage is unchanged). A corrupt stored value opens as the standard names without rewriting anything. Two types may share one label. The names are stored as `typeSubfolderOverrides`, appear in the settings import preview, travel in the portable settings file and use the same path builder for the browser Downloads route, a selected folder and both animation outputs (converted GIF and the MP4 fallback or Reddit HLS result).

Template and filename changes affect new saves. They do not rename or move files already exported. Preserve exact directory receipts for local preview; manually moving a file can make that receipt unavailable. A completed browser download can request Show file in folder by its still-existing native ID. A direct chosen-directory write has an explanatory folder icon because File System Access provides no file-manager reveal action. No companion, native messaging, custom-directory Explorer action or filesystem-wide renamer is present.

For metadata-based filenames, a confirmed multi-file post retains its admitted item
position as `_001`, `_002` and so on, before the extension. This keeps album order
independent of download completion order. A single save has no added index;
original-name mode keeps the source basename. Browser collision numbering can
still be added when an existing file has the same name. This behavior is part of the released foundation.

For TikTok selected-player downloads, original-name mode prefers the verified item ID over the CDN basename, including when that basename is empty. The actual MIME supplies the extension. Composed filename choices, folder templates and collision/no-overwrite behavior still apply. This naming correction is local post-release work; see [status](STATUS.md).

# Changelog

## 3.0.1 — Folder layouts and download recovery

### Русский

- Компактный конструктор подпапок позволяет сочетать уровни в выбранном порядке и редактировать свой шаблон. Предпросмотр пути использует те же правила, что и сохранение. Семейство Booru объединено в одну настройку имени папки; аккаунт загрузившего добавляется только из проверенных метаданных поддерживаемого поста.
- Сохранённая папка различает запрос разрешения, отказ и недоступный дескриптор. Доступ восстанавливается явной кнопкой; отмена смены папки повторно проверяет сохранённую папку и игнорирует устаревшие ответы.
- Составное имя нового файла содержит выбранные доступные поля и расширение без исходного CDN-хвоста. Исходное имя и безопасная нумерация совпадений сохраняются. Для поддерживаемых Danbooru/Moebooru дата и загрузивший аккаунт проверяются по выбранному файлу и посту; неизвестные данные пропускаются.
- Изображения RedGIFs больше не отправляются в видеорезолвер. Поздние ответы закрытой вкладки обрабатываются без необработанной ошибки сообщения; недоступное уведомление не меняет результат загрузки.
- Исправлены скругления popup и ширина русских меток журнала отладки. Красная полоса непрочитанной ошибки удалена; текст, значок и статус ошибки сохранены.
- Действия открытия папок, обходной системный диалог и companion удалены. Сохранение в выбранную папку, восстановление готовых файлов и локальное превью остаются доступны.

### English

- A compact folder builder combines levels in the selected order and supports custom templates. Path previews share the saving rules. Booru sites share one folder-name setting; uploader folders use only verified metadata from supported posts.
- Saved folders distinguish a permission prompt, denial and an unavailable handle. Access restoration is explicit. Discarding a destination change rechecks the saved folder and rejects stale replies.
- Metadata-based filenames contain selected available fields and the extension without the original CDN basename. Original names and safe collision numbering remain. Supported Danbooru/Moebooru dates and uploader accounts are verified against the selected file and post; unknown fields are skipped.
- RedGIFs images no longer enter the video resolver. Late replies from a closed tab consume messaging errors; unavailable page notifications do not change the download result.
- Correct popup corners and Russian debug-level column widths. Remove the unread-error red stripe while preserving error text, icons and status.
- Remove file-manager reveal actions, the system-picker workaround and companion. Chosen-directory saving, retained-file recovery and local previews remain available.


## 3.0.0 — Stable release, GIF encoding and minified builds

Released 2026-10-24: [v3.0.0](https://github.com/xhthc/MediaLatch/releases/tag/v3.0.0).

### Русский

- Собственный код и графика с версии 3.0.0 распространяются по закрытой лицензии. Ранее полученные GPL-версии сохраняют прежние права; лицензии сторонних компонентов не меняются.
- Опубликован подписанный минифицированный CRX с SHA-256 и сведениями о сборке: состав файлов, их размеры и хеши, инструмент минификации и результаты проверок. Подпись CRX3 проверена, все 98 файлов совпадают с принятой сборкой. Закрытый ключ не публикуется.
- JavaScript минифицирован Vite 8.3.5 / Oxc без sourcemaps. Общие глобальные имена и имена свойств сохранены; код остаётся доступным для изучения. CRX не гарантирует установку вне магазина в Chrome для Windows/macOS.
- Кодирование GIF выполняется в отдельном Worker с отменой, тайм-аутом и освобождением ресурсов. Подготовка больше не блокирует поток скрытого документа на кодировании; большие GIF всё ещё требуют времени и ресурсов. На проверенных стендах результат совпадает по байтам.
- ID нового CRX — `iahebdomfekhiofmdocjmdjpjlclnngd`; он отличается от прежней ручной сборки `kmebfblhgfacdonaomlggpkndcjjpkgd`. Установки с другим ID не обновятся этим пакетом; настройки и история автоматически не переносятся.
- Сохранены возможности 2.6.5, включая превью изображений/GIF/MP4, карусель, имена файлов, фильтры типов и офлайн-историю изменений. Новых разрешений, зависимостей или изменений формата локальных данных нет.
- Публикация в Chrome Web Store выполняется отдельно. При включённых Verified CRX Uploads магазин принимает CRX, подписанный зарегистрированным ключом; обычный режим использует ZIP.

### English

- Project-owned code and artwork use a proprietary license starting with 3.0.0. Earlier GPL recipients retain their existing rights; third-party licenses are unchanged.
- Publish a signed minified CRX with SHA-256 and build details: file inventory, sizes and hashes, minifier and validation results. Its CRX3 signature is verified and all 98 files match the accepted build. The private signing key is not published.
- Minify JavaScript with Vite 8.3.5 / Oxc without source maps. Shared globals and property names are preserved; code remains inspectable. A CRX does not guarantee installation outside the store in Chrome for Windows/macOS.
- Move GIF encoding to a dedicated Worker with cancellation, timeout and resource cleanup. Encoding no longer blocks the hidden document's thread; large GIFs still take time and resources. Output is byte-identical on tested fixtures.
- The new CRX ID is `iahebdomfekhiofmdocjmdjpjlclnngd`, different from the earlier manually signed `kmebfblhgfacdonaomlggpkndcjjpkgd` build. It cannot update installations with another ID or automatically transfer their settings and history.
- Retain 2.6.5 behavior, including image/GIF/MP4 previews, carousel, filename settings, file-type filters and offline release history. No new permissions, dependencies or local-data format changes.
- Chrome Web Store publication is separate. Verified CRX Uploads accept a CRX signed with the registered key; the ordinary upload path uses ZIP.

## 2.6.5 — Viewer, naming and lifecycle fixes

### Русский

- Превью изображений, GIF и MP4 открывается в интерфейсе MediaLatch: плеер, зум, перемещение и плавная карусель с кнопками, клавиатурой и свайпом. На недоступных системных вкладках используется менеджер загрузок.
- Имена новых файлов могут включать сайт, аккаунт и дату/время публикации в UTC. Исходное имя сохраняется; при неизвестной дате она не добавляется. Совпадающие имена получают суффикс без перезаписи.
- Убрано вращение шестерёнки. Исправлены прерывания появления/скрытия inline-кнопок и оверлеев; reduced motion действует и на кнопки сайтов. Готовые миниатюры и предпросмотр импорта появляются плавно.
- Повтор загрузки ждёт завершения предыдущей попытки. После перезапуска очищаются завершённые индикаторы загрузки, а восстановленный экспорт сохраняет доступ к своему превью.
- Выбор медиа привязан к исходному документу и жесту; соседние картинки в одной карточке не подменяют выбранный оригинал. Обновлены статистика, ссылки аккаунтов и восстановление локального состояния.
- История изменений листается по версиям офлайн на русском и английском. Счётчик рядом с «Загрузками» стал крупнее и контрастнее во всех темах.
- Новых разрешений нет. Старые или вытесненные оригиналы можно выбрать с диска вручную. Переименование уже скачанных файлов, YouTube-загрузки, DRM и универсальные HLS/DASH не добавлены.
- Учёт нативных загрузок и маршрутизация просмотрщика вынесены в отдельные worker-модули с прежним порядком запуска. Средство разработки Vite закреплено на исправленной версии 8.3.5.

### English

- View images, GIFs and MP4 inside MediaLatch with playback controls, zoom, pan and a smooth carousel with buttons, keyboard and swipe. Restricted browser pages fall back to Download Manager.
- New filenames can include the site, posting account and UTC publication date/time. The original name stays; unknown dates are omitted. Name collisions receive a suffix without overwriting files.
- Remove the rotating Settings gear. Fix interrupted inline/overlay entrances and exits, and honor reduced motion in site controls. Decoded thumbnails and validated import previews appear smoothly.
- Retry waits for the previous attempt to finish. Worker restarts clear completed download indicators; reconciled exports retain their preview identity.
- Media discovery stays bound to the admitting document and gesture. Sibling images cannot lend their original to the selection. Includes statistics layout, account links and local-state recovery improvements.
- Browse bundled release history offline in English and Russian. The Downloads navigation count is larger and has stronger contrast in every theme.
- No new permissions. Older or evicted originals can be chosen from disk. Renaming existing files, YouTube downloads, DRM and universal HLS/DASH are not added.

- Refactor native download tracking and trusted viewer routing into dedicated worker modules; preserve their initialization order and public contracts. Pin the development tool Vite to patched version 8.3.5.

## 2.6.4 — Local preview: selected-image correctness

Local build dated 2026-10-21 for manual sharing. No GitHub or store publication; permissions, dependencies and storage schema are unchanged.

### Русский

- Pixiv: оригинал из API принимается только для выбранной страницы и иллюстрации. Если p5 отсутствует или подменён другим файлом, первая страница не скачивается вместо него. Полная подписанная ссылка сохраняется без изменений.
- Связанные JSON-LD метаданные: слишком большой граф не используется как доказательство уникальности ID; противоречивые сведения о владельце страницы не разрешают загрузку чужого изображения.
- Включены обновлённый UI, миниатюры, ссылки на исходные посты и ранее проверенные исправления восстановления загрузок.
- Это локальное превью. При длительном сбое хранилища статистика ещё может потерять отложенные счётчики; исправление выделено в следующую задачу. Ограничения сервисов и живых страниц остаются прежними.

### English

- Pixiv API originals must match the selected artwork and page. A missing or mismatched p5 never authorizes a p0 substitute. Exact signed URLs remain unchanged.
- Linked JSON-LD metadata: oversized graphs do not prove ID uniqueness, and contradictory page identities cannot authorize an unrelated image.
- Includes the refreshed UI, thumbnails, source-post sharing and previously reviewed download recovery changes.
- Local preview: prolonged storage failures can still lose pending statistical contributions; a separate follow-up is prepared. Existing provider/live-site limitations remain.

## 2.6.3 — Local preview: refreshed UI, thumbnails and YouTube links

### Русский

Локальная сборка от 20.10.2026 для ручной передачи и установки. На GitHub и в магазинах эта версия не опубликована. Проверки на управляемых стендах не заменяют проверку всех сайтов в установленном расширении.

- Обновлены popup и все страницы настроек: иконки сервисов включены в расширение, состояние папок авторов стало понятнее, кнопка сохранения активна только при изменённых настройках.
- Новые сохранённые изображения, GIF и видео поддерживаемых форматов могут показывать локальные миниатюры. Компактное уведомление на исходной странице также может показать маленькую копию из кэша; если её нет, остаётся значок типа файла, без повторного скачивания медиа.
- Одиночные загрузки видны сразу под сайтом, последний пакет поста раскрывается автоматически; лишняя полоса у закруглений пакета убрана. Для GIF добавлен отдельный счётчик, технические данные перенесены в «Подробности».
- Ссылки для превью копируются с обычных видео YouTube и Shorts. По умолчанию видео используют yfxtube.com, Shorts — koutube.com; выбор хранится отдельно в «Превью ссылок». Скачивание YouTube не добавлено.
- Исправлены запоздалое чтение сервиса копирования и возврат фокуса при резервном копировании. Сохранение настроек не выполняется автоматически; понятные состояния и фокус с клавиатуры сохранены.
- Миниатюры ограничены по размеру и числу, хранятся отдельно от статистики и Debug; удаление записи убирает её миниатюру. Старые, неподдерживаемые или вытесненные записи показывают значок файла.

### English

Local build dated 2026-10-20 for manual sharing and installation. This version is not published on GitHub or extension stores. Controlled fixtures do not replace acceptance of every site in the installed extension.

- Refresh the popup and all settings screens with bundled service icons, clearer author-folder toggles and one Save action that is enabled only for changed settings.
- Show optional local thumbnails for newly saved supported images, GIFs and videos. The original source page can also show a tiny cached preview in its compact notice; unavailable previews retain a file-type icon without fetching the media again.
- Show single downloads directly under their site, expand the newest post batch and remove the duplicate line at rounded batch corners. Add a separate GIF statistic and keep technical evidence inside Details.
- Copy preview links from regular YouTube videos as well as Shorts. Videos default to yfxtube.com and Shorts to koutube.com, with separate saved choices in Link previews; YouTube downloading is not added.
- Fix late provider reads and keyboard-focus restoration during clipboard fallback. Settings still use explicit Save; meaningful status and keyboard focus remain available.
- Thumbnail size and count are bounded, separate from statistics/Debug; record removal removes its preview. Older, unsupported or evicted entries retain type icons.

## 2.6.2 — VK previews, clips and download stability

### Русский

20.10.2026 пользователь подтвердил скачивание из превью и сообщил, что клипы скачиваются без ошибок; на снимке есть один сохранённый клип. Текущая работа по VK закрыта по его решению. Большие видео на снимках ещё загружались; звук клипов, полное воспроизведение больших файлов и все варианты страниц этим не подтверждены. Изменения прошли независимое ревью исходников; результаты проверок и точный коммит привязаны к архиву релиза.

- Фото VK: исправлена ошибка INCOMPLETE_BODY. Проверочный запрос с диапазоном (Range, 1 байт) оставлял в HTTP-кэше расширения частичную запись; полная загрузка того же адреса докачивалась из неё, и если CDN отвечал на докачку не 206 (например 429), тело обрывалось после одного байта. Проверочные запросы больше не пишут в кэш. Ответы 429 и проверка тела файла не менялись.
- Клипы VK на vkvideo.ru: кнопки «Скопировать ссылку» и «Сохранить» в левом верхнем углу текущего клипа и сохранение через меню браузера. Файл берётся из собственного действия VK «Скачать» для этого клипа и проверяется как целый MP4. Если VK не разрешает скачать клип, сохранение отклоняется без запасного файла.
- Карточки видео на главной vkvideo.ru и в «Продолжить просмотр»: при наведении или фокусе в левом верхнем углу миниатюры появляются «Скопировать ссылку» и «Сохранить»; то же видео сохраняется через меню браузера по миниатюре, превью или его слою. Видео определяется по ссылке самой карточки и скачивается без открытия; миниатюра не сохраняется. Соседние карточки, аватар канала и прямые эфиры не используются.
- На открытой странице видео vkvideo.ru кнопка «Сохранить» добавлена для подтверждённого плеера с ещё не определённым, blob- или прямым MP4-источником; сохраняется видео этой страницы. Если источник сменился после показа кнопки, нажатие ничего не сохраняет, а при следующем наведении кнопка появляется снова. Сохранение через меню браузера для прямого файла не менялось; если на странице есть второе видео (реклама с источником, превью рекомендации, соседний плеер) или плеер перекрыт, кнопки нет.
- Проверка плеера открытой страницы также требует известную структуру основного плеера и исключает карточки и рекламу: единственный оставшийся соседний ролик больше не получает ID страницы, пока основной плеер отсутствует.
- Оставшееся время загрузки показывается как «4 мин 23 с» или «1 ч 1 мин 1 с», а не только секундами; условия показа не менялись.
- Оценка свободного места браузера (`navigator.storage.estimate()`) больше не отклоняет сохранение: она бывает приблизительной. Реальная ошибка записи (QuotaExceededError) по-прежнему даёт STORAGE_QUOTA; проверки размера, типа файла, отмена и очистка не менялись.
- Журнал диагностики (по желанию) записывает для клипа и других загрузок время ответа API VK, ожидания заголовков и первого байта, загрузки тела, проверки и экспорта, без адресов и токенов. Событие STAGING_PREPARE теперь связано с операцией.
- Исправления: ошибка очистки старых файлов при запуске больше не отключает очередь; отмена и восстановленные записи о папке сохраняют реальное имя файла и отмену; укороченные имена остаются переносимыми. Временный сбой записи состояния операции повторяется при следующем обращении, и настоящая причина (например, нужен вход) не заменяется на «перезапуск»; при постоянном сбое хранилища менеджер не перезагружает список по кругу. Поздний ответ восстановления после перезапуска не возвращает завершённую загрузку во владение offscreen-документа. Неактивные источники <picture> не подменяют показанное изображение; поиск по MD5 принимает ответ только с тем же хэшем и останавливается после него. Если в выбранной папке есть каталог с именем файла, сохраняется «photo (1).png».
- Настройки: сохранение из устаревшей вкладки не возвращает другую папку или подпапку (записываются только изменённые поля); сбой чтения сохранённой папки не блокирует выбор другой, а отмена выбора сохраняет предупреждение; поздний ответ чтения или записи не отменяет новый выбор уведомлений.
- Для разработчиков: `node tools/verify.mjs --native` проверяет расширение в настоящем браузере на локальном стенде CDN (HTTP-кэш, Range, обрыв тела, 429, клипы).
- Упаковка релиза проверяет отложенные импорты и ссылки HTML, а также отклоняет Git-атрибуты, которые исключают или подменяют файлы архива.
- Прямые эфиры и универсальная загрузка HLS/DASH по-прежнему не поддерживаются.

### English

On 2026-10-20 the user confirmed preview downloads and reported clips downloading without errors; the screenshot shows one saved clip. The user closed the current VK work. The large videos were still receiving; this does not establish clip audio, complete large-file playback or every layout. Changes received independent source review; release checks and the exact source commit are tied to the runtime archive.

- VK photos: fix INCOMPLETE_BODY. The one-byte Range probe left a partial entry in the extension's HTTP cache; the full GET of the same address resumed from it, and when the CDN answered that continuation with anything but 206 (for example 429) the body ended after one byte. Probe requests no longer write the cache. HTTP 429 handling and body validation are unchanged.
- VK clips on vkvideo.ru: Copy link and Download buttons in the upper-left corner of the current clip, and browser-menu saves. The file comes from VK's own Download action for that clip and is checked as a complete MP4. If VK does not allow downloading the clip, the save is refused with no fallback file.
- Video cards on the vkvideo.ru home and Continue watching: hover or focus shows Copy link and Download in the upper-left thumbnail corner; the browser menu on the thumbnail, preview or its overlay saves the same video. The video comes from the card's own link and is downloaded without opening it; the thumbnail is never saved. Neighbouring cards, the channel avatar and live streams are not used.
- An opened vkvideo.ru video page has Download for its proven player whether its source is unresolved, a blob or a direct MP4; it saves the video of that page. If the source changes after the button was shown, the click saves nothing and the button returns on the next hover. Browser-menu saving of a direct file is unchanged; with a second video on the page (a sourced ad, a recommendation preview, a neighbouring player) or a covered player there is no button.
- Opened-page player proof also requires the observed main-player structure and excludes card/ad ancestry: a lone unrelated video no longer borrows the page ID while the main player is absent.
- Remaining download time reads "4 min 23 s" or "1 h 1 min 1 s" instead of seconds only; when it is shown has not changed.
- The browser's storage estimate (`navigator.storage.estimate()`) no longer refuses a save: it can be approximate. A real write failure (QuotaExceededError) still reports STORAGE_QUOTA; size, file type, cancellation and cleanup checks are unchanged.
- The opt-in diagnostic journal records the VK API wait, the wait for headers and first byte, the body transfer, validation and export as numbers, with no addresses or tokens. STAGING_PREPARE events now carry their operation.
- Fixes: a cleanup error at startup no longer disables the queue; cancellation and restored folder receipts keep the real filename and the cancellation; shortened names stay portable. A transient failure to write operation state is retried on the next access, and the real reason (for example sign-in required) is not replaced by "restart"; a persistent storage failure no longer makes the manager reload its list in a loop. A late recovery answer after a restart no longer returns a finished download to the offscreen document's ownership. Inactive <picture> sources no longer replace the displayed image; the MD5 lookup accepts only an answer with the same hash and stops after it. A directory named like the output file makes the save use "photo (1).png".
- Settings: saving from a stale tab no longer puts back another tab's folder or subfolder (only changed fields are written); an unreadable saved folder does not block choosing another, and cancelling the picker keeps the warning; a late read or write no longer overrides a newer notification choice.
- Developers: `node tools/verify.mjs --native` checks the extension in a real browser against a local CDN fixture (HTTP cache, Range, truncated bodies, 429, clips).
- Release packaging checks deferred imports and HTML references and rejects Git archive attributes that omit or rewrite runtime files.
- Live video and general HLS/DASH downloads remain unsupported.

## 2.6.1 — VK Video, export recovery and local release notes

### Русский

- Видео с обычных страниц vkvideo.ru можно скачать через меню браузера. Экспериментальная поддержка использует объявленный самим видео MP4-файл; inline-кнопки на этом сайте не добавлены.
- После перезапуска фонового процесса уже принятые операции сохранения могут завершиться даже при паузе очереди или ожидании после ошибки источника. Повторного скачивания с сайта нет.
- В «Обновлениях» показаны только изменения последнего релиза на русском и английском. Они доступны без интернета; стрелки версий и счётчик страниц убраны.
- Убрана заливка при наведении на разделы настроек и строки changelog. Исходное всплывающее меню загрузок сохранено.
- Клипы VK, прямые эфиры и универсальная загрузка HLS/DASH не поддерживаются. Другие варианты плеера VK Video ещё требуют проверки.

### English

- Save selected videos on ordinary vkvideo.ru video pages through the browser menu. This experimental path uses the video’s declared MP4 file; inline buttons are not added there.
- After a background-worker restart, already accepted file exports can finish even when the download queue is paused or the source is waiting after an error. The source is not downloaded again.
- Updates shows only the latest release notes, bundled in English and Russian and readable offline. Version arrows and the page counter are removed.
- Remove hover backgrounds from settings navigation and changelog rows. The original download popup is retained.
- VK clips, live video and general HLS/DASH downloads remain unsupported. Wider VK Video layouts still need testing.

## 2.6.0 — VK video recovery, bulk saves and UI polish

- VK feed and opened videos: a Download control appears over the selected video (its linked poster before playback, the playing player after), and the browser menu's MediaLatch: Save media on the same video takes the same route. Both resolve that exact video's own declared progressive file through VK's video metadata (matching owner and id, highest declared quality, MP4 bytes verified) and use the posting account for author folders. A recycled, replaced or navigated player, another video's metadata, live/DRM, stream-only or unavailable videos are refused visibly; a poster, a neighbouring post or the page's stream is never saved instead. Browser-menu saves additionally re-prove the pressed surface and bind the original source/link, gesture and document. The user confirmed the tested vk.ru/vk.com feed/post inline and browser-menu paths before and after playback. The separate vkvideo.ru player, clips and other layouts remain unsupported or unverified.

- Browser-menu image saves read the selected image's `srcset` the way browsers do: compact lists without spaces after commas (`a.jpg 400w,b.jpg 1200w`), commas inside a URL (CDN transforms, data URLs), fractional and exponent densities (`.5x`), and invalid or duplicate descriptors, which drop only that candidate. The larger listed variant of the selected image is saved instead of its small one; the existing candidate ranking is unchanged.
- Images and videos inside closed (and nested) Web Component shadow roots can be saved from the browser menu: the right-click, the keyboard menu and the menu hint select the exact pressed node through `chrome.dom.openOrClosedShadowRoot`, and its own `srcset`/`<picture>` metadata is used. A moved, replaced, covered or re-sourced component, a navigated frame or an untrusted gesture refuses the save; when the pressed media cannot be seen, only the selected URL is saved, never a neighbouring image or page metadata.

- Keep already prepared files when storage/offscreen verification fails or returns no usable answer. Restart, export and retry distinguish an unknown verification result from a confirmed missing/corrupt file; a transient error no longer discards the local copy or triggers a second source acquisition.

- VK menu selection is captured on trusted right-press and kept separate from cursor/focus hints, so those hints cannot discard an already selected video. The inline button stays reachable when the pointer enters its icon.
- Bulk photo downloads preserve successful HTTP probe evidence and avoid repeated successful HEAD requests. VK photo HEAD404 responses get a bounded GET at the exact same signed address; unavailable sources still fail. The user accepted bulk saves during scrolling.
- Tighten settings spacing and add short interface motion; preserve reduced-motion behavior. Refresh EN/RU wording and retain the original README layout, badges and store/download buttons. Batch cancellation uses an icon-only action with an accessible label.
- Remove the unused shadcn CLI development dependency and its vulnerable braces chain. Copied UI components, notices, runtime dependencies and generated extension assets stay in place.

## 2.5.9 — TikTok/Reels controls, author folders and staging reliability

- TikTok and Instagram Reels: optional author folders now use the posting username from the exact item that supplies the selected video file, for inline and browser-menu saves. Both existing folder layouts and saved folder preferences apply; an unknown or invalid username keeps the ordinary layout. Download cards retain the proven account.

- Instagram Reels (Reels feed and opened Reel): Copy link above Download in the upper-right corner of the selected Reel's video, shown on hover over that video, hidden on exit, reachable by keyboard and always visible without hover; they replace the earlier Reel Copy above Like (ordinary posts unchanged). Download saves the Reel in view through the existing selected-video resolver and manager only when the player's own item matches the Reel's proven shortcode; covered, neighbouring, recycled or separate-track-only Reels are refused visibly, and a double press makes one job.

- TikTok: reveal Copy link and Download only while the pointer is over their video, and hide them on exit. Keyboard focus keeps both actions visible; devices without hover keep them available.

- TikTok: separate Copy link and Download buttons directly below the video's native More (⋯) icon. Their local media anchor follows scrolling, resizing and card replacement without altering TikTok's menu or avatar/action rail. It saves the card's own video through the existing proven-player resolver and download manager (exact signed address); a covered, offscreen, recycled or ambiguous player is refused visibly, and a quick double press makes one job.
- TikTok: Copy link no longer appears inside TikTok's right-click menu or at an unproven player/container location, and an extra copy placed by an earlier version is removed. Cause: a selector list picked the player section before the action rail, every container of a card was injected separately, and the Share scan matched the menu's Share item.
- TikTok right-click: a plain right-click keeps TikTok's own menu; Shift+right-click on the player now reliably opens the browser menu with MediaLatch: Save media. Cause of the earlier instability: the press lands on TikTok's overlay outside the player wrapper, where the previous rule did not apply.

- Harden disk-backed staging cancellation during validation/commit, same-job replacement file identity and full-versus-unknown quota handling; failed transfers release their source.
- User checks confirm TikTok/Reels controls, saved audio, embed links and username folders. Broader feed/layout, separate-track streams and crash/full-disk coverage remain limited.
- Update EN/RU documentation and privacy disclosures, and separate implemented extraction/MV3 safeguards from future universal-media work in [the architecture roadmap (private maintainer reference)](https://github.com/xhthc/MediaLatch-Release/blob/main/docs/ROADMAP.md). No new permission, dependency or storage schema.

## 2.5.8 — tested inline scope and experimental social videos

- Limit inline download controls to tested X/Twitter, Reddit, Pixiv, RedGIFs and VK surfaces. Remove the generic control and worker route that caused false positives on unrelated pages. Preserve browser context-menu saving, Instagram/TikTok author-folder proofs and copy/embed actions.

- Replace the paperclip-like share glyph with the existing Lucide Copy icon across X, Instagram, TikTok and YouTube Shorts. One shared outline glyph keeps its full viewport and inherits the button color; copied links, selected embed hosts and action placement are unchanged.

- Add experimental selected-video saving for TikTok and Instagram Reels/video posts through the browser context menu. Bind the progressive file to the gesture-selected player and its own item metadata, preserve exact signed URLs, and use the existing manager. TikTok's header rule is limited to the extension's own CDN requests. Separate DASH tracks remain unsupported; full feed and audible-playback acceptance remain pending.
- Reject underlying TikTok/Instagram players when the pressed login/modal/consent surface does not contain that player. Retain legitimate player viewing dialogs; cover both cases with no-request and exact-file regressions.

The user confirmed that unrelated-page inline false positives are gone. Existing tested-site photo and download-manager acceptance is retained. TikTok/Instagram video support is experimental: recorded native Instagram export and separate TikTok acquisition evidence do not establish every live selection/feed layout or audible playback. No new permission, dependency or storage schema; this is a GitHub pre-release, with Chrome Web Store publication separate.

## 2.5.7 — generic inline saves and Show in folder

- Show in folder in the popup and the full Downloads manager reveals the exact saved file of a finished browser download (also a renamed "photo (1).jpg") through `chrome.downloads.show`; a refusal stays on that card. Chosen-folder exports have no browser download record and show no icon.
- The three header rules for Pixiv, anime-pictures and Gelbooru CDNs now apply only to MediaLatch's own requests to those exact domains; normal browsing and lookalike domains are untouched.
- Generic Save this control on other http(s) sites for individual, directly declared image/video files. Posting-account labels and optional author folders also cover VK, RedGIFs, Instagram and TikTok; an account is given only when the media is evidently the post's own attachment, so comments, replies, quotes (also without a profile link), header avatars and profile-linked media do not get the post's account.
- One shared list each for author-folder services and for hosts with their own inline controls; one inline route registry and one sender check in the worker; one proof listener per page. No permission or dependency added.

- Organize import provenance under `docs/history/` and browser diagnostics under `tools/diagnostics/`; refresh both READMEs and current architecture/release guidance. Runtime entry points stay at the extension root.

Independent source/UI checks passed 87/87 on the reviewed runtime candidate. The user confirmed Embed and Explorer file selection in Helium. Expanded live account attribution, original-photo quality, general VK videos/clips and broader browser support remain unclaimed. This is a GitHub pre-release; Chrome Web Store publication is separate.

## 2.5.6 — VK photo carousels and collages

- Keep VK inline controls at a constant offset from the media’s own upper-left corner, moving with the media rather than following the viewport. Preserve safe hiding for offscreen or covered targets.
- Recover selected carousel photos beneath navigation layers and zero-size links; support 90px collage thumbnails without losing either Save this or Save all.
- Offer Save all for the exact complete, intrinsically owned carousel or grid; exclude neighboring posts, comments, nested reposts and hidden +N remainders. Count declared offscreen photo sources without requiring every slide to decode first.
- Preserve every mixed-post slot. For linked video tiles already included in an admitted post, resolve matching first-party progressive metadata, verify MP4 bytes and use the existing save pipeline; retain cancellation and duplicate guards. This is limited mixed-post handling, not general VK video support.
- Refresh EN/RU coverage and roadmap. Standalone VK videos and clips are deferred to a separate planned increment; GIF is not required. Permissions, dependencies and UI assets are unchanged.

The user confirmed that VK carousels and collages save correctly. Recorded native checks include selected photos, observed complete photo lists and a seven-item mixed post (five JPEGs, two MP4s with structurally present audio tracks). Original-photo quality, broad video/clip coverage and audible playback are not established. This remains a GitHub pre-release; the Chrome Web Store listing is unchanged.


## 2.5.5 — author labels and experimental VK inline

- Show proven X/Reddit/Pixiv authors in page notices, popup and full Downloads; preserve attribution through batches and retries. Unknown authors and older records omit the label.
- Balance the popup's left/right download gutters while retaining its translucent custom scrollbar.
- Add experimental vk.ru/vk.com inline controls for a loaded selected photo or an opened direct HTTPS video/clip file. Freeze the selected source; never substitute a poster or rediscover a neighboring target.
- Place VK controls at the visible upper-left corner, retain the selected media while scrolling and clear a full-width fixed/sticky header. Hide safely for changed, removed, offscreen or covered targets.
- Offer VK Save all only when intrinsic post identity and one complete attachment list are proven, up to 100 files; never claim a rendered subset is the whole post. Add the VK service label/category without inventing historical attribution or authors.
- Redact known short and long signed query values in diagnostic logs, including duplicate-download and provider fallback paths.
- Refresh English/Russian coverage, roadmap, privacy and release instructions; keep screenshot version provenance. Allow 180 seconds for the existing UI render suite after a measured 142-second run exceeded its prior 120-second harness limit. Assertions are unchanged.

This is a GitHub pre-release. The user confirmed VK button appearance after hard reload; placement has isolated headless Helium fixture evidence. Live VK inline export, original-photo parity, complete-post layouts and video/clip/audio coverage remain unverified. The requested full VK increment is unfinished. Earlier X/Reddit/Pixiv/RedGIFs, author-label and Downloads user acceptance is retained. Chrome Web Store 2.5.2 was reportedly approved/published and then accidentally unpublished; this preview does not republish the listing.


## 2.5.4 — shared inline controls and compact downloads

- Add Pixiv inline Save this / Save all for proven artwork pages and supported feed cards; retain original selection and the 100-item batch cap. Fix page-count detection so numeric author names are not mistaken for media counts.
- Consolidate X, Reddit, Pixiv and RedGIFs inline controls into one shared module, organize runtime modules and strengthen hostname boundary checks without adding site support automatically.
- Add Cancel remaining for a post batch in popup and full Downloads; completed exports and unrelated jobs are preserved.
- Group all single and batch downloads by site, promote the site only for a new request, and separate compact Individual files and post subgroups. Finished subgroups start folded; notification links reveal their exact file. Original request time and source ordering survive queue recovery.
- Use the same bounded, translucent custom scrollbar in popup and settings, with fixed popup header/footer.
- Replace in-flow Embed help with themed floating bubbles, keep keyboard/tap access, and fix stale bubbles after rapid pointer exit. Limit Theme/Language hover highlighting to the select trigger.
- Refresh EN/RU release documentation, roadmap status and neutral Downloads/Embed captures. Permissions, dependencies and storage schema remain unchanged.

This remains a pre-release. Accepted changes have independent reviews, automated/isolated browser checks and bounded user confirmation of the four inline sites, Downloads and settings help. Exact committed runtime packaging is checked separately. Exhaustive live-provider/audio, other-browser, crash/quota and store-approval claims remain outside this release; the submitted Chrome Web Store 2.5.2 archive is unchanged.

## 2.5.3 — post-batch progress and site statistics

- Show one durable post summary in both managers for X/Reddit Save all, multi-page Pixiv artworks and multi-original Pawchive posts. Saved, failed, cancelled, skipped and remaining counts stay distinct; retries update the existing item.
- Keep one updating notice per post using committed manager counts. Partial Pawchive imports retain their unavailable-original diagnostic and never claim all post files were saved.
- Add compact local site statistics: populated services only, one Booru view, preserved all-time totals and conservative legacy attribution. Recording and clear remain global.
- Preserve known owning-service attribution through queued retries and worker recovery, including prepared outputs after recent feedback expires.
- Remove the repeated download-row tooltip/hover overlay and move terminal record removal into the full manager's expanded details.
- Refresh EN/RU release documentation, roadmap status and neutral downloads/statistics captures. Permissions, dependencies and provider admission rules are unchanged.

This remains a pre-release. The accepted feature code passed 77 GitHub checks, independent source reviews, isolated native byte/restart checks and bounded user Helium acceptance for X/Reddit batches, statistics and live Pixiv/Pawchive results. These do not establish exhaustive provider/audio, Google Chrome, quota or crash coverage. The submitted Chrome Web Store 2.5.2 package is a separate, unchanged build.

## 2.5.2 — media request guards and project cleanup

- Include the reviewed interface cleanup and project file organization while preserving download workflows and stored preferences.
- Restore the original seven-item sidebar without category captions or collapse controls.
- Add `kkclip.com` as an optional Instagram link-preview host; keep existing hosts and explicit Save settings.
- Publish the reviewed runtime as a GitHub pre-release; keep Chrome Web Store artwork and upload materials outside the repository and release assets.
- Remove the unused documentation banner; retain runtime code, build sources, fixtures, licences and product screenshots.
- Restrict privileged offscreen commands to the worker and reject synthetic converter IPC fields.
- Refuse literal local-network media from public pages and unchecked redirects; preserve deliberately selected local-page media. Hostname DNS changes remain outside this guard.
- Bound Zerochan metadata to 2 MiB with cancellation throughout its deadline.

Store submission and approval are separate states. User-reported X, Reddit and RedGIFs checks were performed in Helium; this does not establish Google Chrome, all-provider or audio acceptance.

## 2.5.1 — redesigned interface and violet gradient branding

- Redesign the manager, popup, settings, statistics and diagnostics with grouped navigation and consistent panels across Violet, Blue, Dark and Light themes. Preserve English/Russian localization and existing preferences.
- Make link-preview settings a responsive two-column grid with help for each platform; preserve explicit Save settings and all existing preview hosts.
- Align notification/Debug switches with their panels; retain popup wheel/keyboard scrolling and the global finished-record clear action.
- Refresh the recognizable M/download icon with a violet three-stop gradient and subtle edge; synchronize UI, toolbar theme variants and notification assets.
- Replace EN/RU README screenshots with actual isolated-browser captures; update current privacy details and prepare neutral Chrome Web Store screenshots and promotional art.

This remains a pre-release. Download providers, privileged boundaries, storage keys, permissions and dependencies are unchanged. Existing provider smoke evidence is retained; independent source review, UI verification and exact-package browser/export checks are recorded for this preview. No store approval, exhaustive live-provider/audio or performance/leak result is claimed.

## 2.5.0 — version update

- Repackage the accepted 2.0.0.33 runtime as version 2.5.0; extension behavior, permissions, dependencies and stored data are unchanged.
- Update current release links and installation archive names in the EN/RU README.

This remains a pre-release. Prior source and browser validation applies to the unchanged runtime; packaging and version/update checks are repeated for the new archive.

## 2.0.0.33 — author folders, selected-media continuity and refactor

- Add a separate first-install welcome with one Continue action to Saving; keep it dismissed after updates and restarts.
- Add one Author folders menu for x.com, Reddit and Pixiv. Preserve the previous X preference; Pixiv folders use author name plus user ID. Keep flat and site/type organization choices.
- Improve original Pixiv preview acquisition through staged downloads with progress and a durable 50 MiB cap. Preserve the selected post, author and batch when feed nodes scroll away or are recycled; keep document/navigation and ownership refusals.
- Strengthen declared-original ownership for booru engines and Zerochan; preserve existing rate/access, MIME and file-identity checks.
- Match interface and toolbar icons to Violet, Blue, Dark and Light themes. Keep popup wheel scrolling with hidden rails and one global clear action; per-file removal remains in the full manager.
- Split worker candidates, booru adapters, selected-frame reads and X recovery into focused modules. Remove unreachable legacy history/UI/helpers and fold equivalent repeated branches without changing stored preferences or statistics migration.
- Refresh EN/RU README and interface screenshots for this preview.

Validation: reviewed refactor72/72 checks and seven-file UI build parity, independent source review, isolated Chromium startup/UI/legacy-statistics/restart checks, and limited user-reported Helium saves/interface smoke tests. This prerelease does not establish exhaustive audio/byte, crash/quota or performance/leak coverage. Rapid RedGIFs inline saves can hit the existing four-active admission limit; the current RATE_LIMIT label also covers remote HTTP429.

## 2.0.0.32 — remove Explorer integration

- Remove the Windows Explorer companion, native messaging permission and destination-link setup. Saving to custom folders and per-author subfolders remains available without companion software.
- Remove file-location folder icons from both download managers and retire their worker/controller actions. Existing downloads, saved files, preferences and manager-return notices are retained.
- Withdraw the v2.0.0.31 companion release assets. Earlier runtime archives remain historical builds; use v2.0.0.32 for the rollback.

This is a preview. Automated checks do not establish broad live-site or installed-popup acceptance.

## 2.0.0.31 — manager-return notices and Windows Explorer

- Keep page notices working after opening the download manager and returning to the source page. Opening the manager retires the current card; later results still share one activity card. Explicit close/Escape retains series suppression.
- Replace the chosen-folder file picker with an optional Windows Explorer companion for both download managers. Link a saved destination once; verify the exact extension origin, fresh directory proof and completed relative file before opening its parent. Ordinary browser Downloads keep their existing reveal action.
- Provide the Windows companion as a separate release ZIP with installation instructions. Missing helper/binding keeps download cards and gives localized recovery. The extension now declares `nativeMessaging`.

The user confirmed the manager-return notification fix. Automated68/68 checks and isolated native manager navigation/host communication passed. Actual Explorer/external-folder proof/toolbar lifetime and broader site/audio/crash/quota checks remain pending; this is a preview. Earlier release tags and assets stay unchanged.

## 2.0.0.30 — grouped notices and file locations

- Separate worker provider, pipeline, animation and offscreen lifetime modules; share checked download contracts with the UI while preserving media guards and existing save behavior.
- Group bulk-save page notices into one stable activity card with localized outcome counts and dismissal suppression.
- Keep the toolbar badge stable through parallel/queued downloads; preserve readable errors and guard stale asynchronous updates.
- Add file-location buttons to completed download cards. Browser downloads reveal through the OS file manager; chosen-directory writes use a browser picker at the stored file's actual parent. Preserve cards on failure and keep picker cancellation silent.

Automated regressions, source/build parity and isolated extension fixtures passed. Real Windows file-location dialogs, actual toolbar-popup lifetime and broader manual regression gates remain pending. This preview includes these changes; earlier release assets and tags are unchanged.

## 2.0.0.29 — organized source and current interface

- Organize site scripts in `content/` and offline checks in `tests/`; extract existing worker format, destination/naming and dedicated-site resolver modules without changing their behavior. Update runtime injection and commit-based packaging paths.
- Make Violet the default theme, refresh saving/link settings and the EN/RU visual README. Add destination-folder selection and optional x.com author folders.
- Receive files concurrently, support declared post batches up to 100 files, and clear the manager list immediately. Preserve selected-original and truthful format validation.
- Replace desktop notifications with bounded MediaLatch page notices. Add short menu/disclosure/notice transitions and smooth committed language changes, respecting reduced motion and mounted drafts. Display x.com consistently.

- Add persistent Blue, Dark and Light themes across extension pages.
- Replace retained-history totals with configurable, clearable aggregate Statistics; import only legacy records still available locally.
- Stage and validate complete files in private disk-backed browser storage before exporting prepared bytes. Show stages, received/total, speed and approximate time when measurable, queue pause, cancellation and explicit retry.
- Merge progress, controls and result/report details into one download card; fix long Russian tab labels and keyboard visibility on narrow windows.
- Preserve pending statistics and refuse unpersisted record removal; keep signed source addresses out of public snapshots and reports.

User-confirmed ordinary Helium checks and isolated native transfer/UI fixtures passed. Native crash/restart, quota stress and broad codec/audio acceptance remain pending. These changes ship in v2.0.0.29 preview; this is not complete browser or store acceptance.

## 2.0.0.28 — Sankaku originals and bounded metadata

- Resolve selected Sankaku preview/sample media to the same post's declared original, preserving its exact signed URL and real format instead of saving an AVIF thumbnail. Refuse ambiguous or inaccessible originals.
- Allow one bounded authenticated same-origin post-page lookup when the original is not in the current DOM: 20-second deadline through headers/body, 1 MiB HTML limit, selected-node continuity and specific network diagnostics.
- Bound generic MD5 metadata reads to 3 seconds through headers/body and 1 MiB of streamed bytes; cancel refused, failed and completed transfers. A stalled or oversized response no longer holds up this lookup indefinitely.
- Update English/Russian README coverage and roadmap. Add a security/store-readiness plan; Kemono remains deferred.

Preview validation: independent source review, production-path offline regressions and UI parity checks. The user reports working Sankaku image/video smoke tests in Helium. Native Sankaku GIF testing is pending because search was unavailable under the site's reported rate/subscription limits. This is not a completed security audit or Chrome Web Store approval.

## 2.0.0.27 — save fixes and optional debugging

- Add an opt-in local Debug panel with correlated content/frame/worker/UI events, filters, copy/export and clear controls. Bound the journal to 2,000 events, 1 MiB and 24 hours; omit full URLs, tokens, page text and local paths.
- Correct selected X quote owners, lazy media lookup before playback and multi-video Save all batches.
- Restore inline controls and first-click saves after feed scrolling and frame changes, including Reddit/RedGIFs. Start runtime injections immediately in loading frames.
- Preserve supported Reddit HLS audio and playback seeking; report Pawchive originals that the site has not imported.
- Save the verified source MP4 when X/Reddit animation conversion exceeds input or encoded GIF size limits. Keep existing limits and unrelated error handling; describe the MP4 result in save feedback.
- Preserve machine-readable conversion failure codes in Debug reports.

Preview validation: 42/42 automated checks on the accepted implementation and user-confirmed reported X, Reddit and RedGIFs cases in Helium. Other layouts, browsers and oversized-input native behavior remain outside that acceptance.

## 2.0.0.26 — MediaLatch and English / Russian

- Rename the product and repository to MediaLatch with a new M/download mark; keep existing preferences and save folders compatible. Runtime assets use the MediaLatch prefix.
- Add a persistent English / Russian interface choice across extension pages, notifications and inline labels.
- Keep the context-menu action fixed as MediaLatch: Save media; original discovery still starts after choosing it.

- Fix stale inline translations, language-change write races and repeated RedGIFs subscriptions; keep compact Russian save-all labels within their existing width.
- Update release checks and current project links after the repository rename.

The first public preview below retains its original Image Saver name and asset names.

## 2.0.0.25 — first public preview

### Release preparation

- Publish current product source, ready-built UI, tests and clean commit-based runtime packaging.
- Add English/Russian documentation, privacy details, store preparation notes and extension icons.
- License project-owned code as GPL-3.0-only; restore complete bundled notices.
- Point release checks at xhthc/ImageSaver and discard the old repository's cache.

### Fixes

- Prevent unreadable saving settings from being overwritten with defaults.
- Bound and validate buffered Pixiv images; keep the request deadline active while reading.
- Cap GIF conversion input and RedGIFs metadata before full buffering.
- Redact Reddit/CDN signatures in diagnostic copies without changing actual URLs.
- Replace two UI components with a small Radix tooltip and CSS fade for clear redistribution terms.

### Included earlier work

- Constant Image Saver: Save media menu title; discovery after choosing Save.
- All declared Pawchive post originals from feed previews, including covers and numbered CDN sources.
- Provider-selected inline saves and restricted Reddit HLS assembly.
- One eligible browser-native resume attempt on NETWORK_FAILED.

Kemono integration, a general download manager, universal selection, ZIP batches, arbitrary drive paths and Firefox support remain planned. Native acceptance of this preview's hardening changes and Chrome Web Store submission remain separate steps.

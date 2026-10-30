# Changelog

## 3.0.7

Stable GitHub release with verified owner-signed minified CRX and matching runtime ZIP. Chrome Web Store rejected draft 3.0.7 on 2026-10-31 for excessive site keywords (Yellow Argon). Revised English and Russian descriptions remove the lists; resubmission and approval remain separate.

### Русский

- Настройки папок и имён файлов (структура папок, названия сайтов и типов, шаблон и область применения имён, источник даты, номер в серии, подтверждённые автор и дата публикации) теперь передаются во все пути сохранения через один явный список. GIF-конвертация, Reddit HLS, общий конвейер, аварийный запасной путь и универсальный сборщик ведут себя как раньше; тесты проверяют эти пути целиком, а не считают строки исходного кода.
- Одно сохранение — одно место: выбранная папка (или обычные «Загрузки»), которую сохранение зафиксировало вместе с настройками папок и имён, остаётся за ним, даже если место сохранения изменили, пока файл ещё определялся или конвертировался. Раньше такое сохранение могло сочетать старую структуру папок с новой выбранной директорией. Сохранения, начатые позже, используют новую настройку; повтор уже поставленной в очередь загрузки сохраняет её место. Выбор папки никогда молча не превращается в сохранение в «Загрузки».
- Проверка владельца миниатюры использует узкий запрос менеджера вместо создания полного публичного списка истории для каждой видимой строки. Проверки задания, операции и состояния, ожидание инициализации и записи сохранены; доступ к оригиналу и ограничения импортированной истории остаются отдельными.
- Облачные хранилища (исходники, без живой приёмки): раздел **«Хранилища»** и выбор места сохранения в «Сохранении» и во всплывающем окне отправляют новые файлы на этот компьютер, в Google Drive или на Яндекс Диск с теми же структурой папок, названиями и правилами имён; недостающие папки создаются. Подключение — входом через OAuth или (в «Дополнительно») токеном доступа, который сначала проверяется у сервиса и только потом заменяет прежнее подключение (API-ключ отклоняется). Файлы грузятся прямо из браузера, имеют сохранённую приватную квитанцию, показывают реальный этап загрузки и считаются сохранёнными только после подтверждения сервисом; ненастроенное, отключённое или просроченное облако отклоняется и никогда не заменяется сохранением на компьютер. Добавлено разрешение `identity`, новых доступов к сайтам нет. Настройка, ограничения и ещё не выполненная живая проверка: docs/CLOUD.md.

- У локального и каждого облачного хранилища отдельные профили папок и имён; универсальная настройка заполняет все три профиля, сохраняя их подпапки. Место в облаке показано под левой навигацией во всех разделах. Уточнены переходы и уменьшение движения; иконки настроек, паузы и корзины в popup неподвижны.

- Имена файлов: выберите, к каким сервисам они применяются (все, часть, Booru одной группой или другие сайты), и источник даты — начало скачивания или публикация (если известна). «Универсальная настройка» одним нажатием заполняет форму: папки сайт / автор / тип, папки авторов, имена дата + время + сайт + автор для всех сервисов с датой начала скачивания. Сохранение остаётся явным; существующие файлы не переименовываются.
- Ускорены поиск по имени, автору и сайту, подготовка и группировка больших списков загрузок. Порядок файлов, фильтры и счётчики сохранены.
- Убраны повторные подключения общих библиотек на поддерживаемых сайтах; повторное внедрение сохраняет каталог переводов и уже показанные подписи.
- Веб-страницам доступен только вход во встроенный просмотрщик. Его JavaScript/CSS остаются приватными; проверки токена, вкладки и документа сохранены.
- Добавлено разрешение `identity` для облачного входа. Новых доступов к сайтам и зависимостей нет; история сохраняет прежние ограничения доступа, токены не экспортируются.
- Ускорение подтверждено синтетическими замерами, а история из 5000 записей — отдельным профилем Chromium. Это не измерение общей RAM браузера и не проверка всех живых сайтов; работа Embed зависит от сторонних сервисов.

### English

- The folder and file-name preferences (folder layout, per-site and per-type labels, name template and service scope, date source, batch position, proven author and publication date) are now forwarded to every save path through one explicit projection. Converted GIFs, Reddit HLS, the shared pipeline, its emergency fallback and the generic builder behave exactly as before; regression tests now exercise these paths end to end instead of counting source text.
- One save, one destination: the chosen folder (or browser Downloads) that a save captured together with its folder and name preferences now stays with it, even if the Saving destination changes while the file is still being resolved or converted. Before, such a save could combine the old folder layout with the newly chosen directory. Saves started afterwards use the new setting; retries of an already queued job keep that job's destination. A folder choice is never silently turned into a Downloads save.
- Thumbnail ownership checks use a narrow manager query instead of constructing the complete public history for each visible row. Exact job/operation/state checks and initialization/write barriers remain unchanged; original file access and imported-history limits stay separate.
- Cloud destinations (source, not live-accepted): a **Storage** section and a destination chooser in Saving and the toolbar popup send new saves to this PC, Google Drive or Yandex Disk, using the same folder layout, labels and file-name rules and creating missing folders. Connect by OAuth sign-in, or under *Advanced* with a pasted access token that is validated with the vendor before it replaces anything (an API key is refused). Uploads go straight from the browser to the provider, keep a durable private receipt, show a real upload stage and count as saved only after the provider confirms the stored file; an unconfigured, disconnected or expired cloud is refused and never turned into a PC save. Adds the `identity` permission and no host permissions. Setup, limits and the live-acceptance still owed: docs/CLOUD.md.
- Inline Save always targets this PC; one compact Cloud segment offers a connected provider and selected/all gallery scope. Popup and ordinary context-menu saves retain their global destination. Cloud receipt recovery and cached Drive folder parent/name checks preserve the original account and configured path.
- No new dependencies or data-format changes beyond the cloud receipts above.
- Keep separate folder/name profiles for this PC and each cloud; Universal setup fills all three while retaining their subfolders. Show cloud capacity below the left navigation in every section. Refine transitions and reduced motion; popup Settings, Pause and Trash icons remain stationary.

- File names: choose which services they apply to (all, some, Booru as one group, or other sites) and the date source: download start or publication (when known). “Universal setup” fills the form in one click: site / author / type folders, author folders, and date + time + site + author names for all services dated by download start. Saving stays explicit; existing files are not renamed.
- Speed up filename, author and site searches, list preparation and grouping for large download histories. Preserve file order, filters and counters.
- Remove repeated shared-library registrations on supported sites; reinjection preserves the translation catalogue and existing labels.
- Expose only the embedded viewer entry to websites. Keep its JavaScript/CSS private and preserve token, tab and document checks.
- Add the `identity` permission for cloud sign-in. No new host permissions or dependencies; history retains its access limits and tokens are never exported.
- Speedups are supported by synthetic measurements and a 5000-row history by an isolated Chromium profile. This does not establish whole-browser RAM savings or every live site; Embed playback depends on third-party services.

## 3.0.6

Stable GitHub release with a verified owner-signed minified CRX and matching runtime ZIP. The registered signature and all 104 payload files match the corrected build. Chrome Web Store submission, review and approval remain separate owner actions.

### Русский

- Recent Downloads растёт по числу видимых файлов до нижнего края левой колонки статистики, затем прокручивается внутри. При сворачивании групп высота уменьшается без пустого хвоста. Устранён цикл пересчёта размеров при изменении списка.
- Исправлены панели Instagram Reels, Copy/Save в модальном плеере профиля TikTok, кнопка Tumblr и её привязка к исходному посту, а также наведение на Copy в Twitch clips.
- e-shuushuu распознаёт вариант /large/ и восстанавливает поиск оригинала при недоступном API. Для фото VK сохраняется подтверждённая ссылка исходного поста.
- Отклонённый inline-запрос теперь явно сообщает об отказе без ложного перехода в загрузки. Проверки выбранного поста, кадра и источника сохранены.
- Повтор неопределённого результата сохранения проверяет уже записанный файл через тот же барьер подтверждения, не обходя отказ и не перезаписывая файл.
- Обычная лента Instagram пропускает ненужный поиск панели Reels; скрытые загрузки останавливают таймер устаревшей скорости, а добавление превью не переписывает неизменившиеся записи.
- Узкая навигация показывает выбранный раздел; панель сохранения настроек не закрывает редактируемое поле. Уточнены уменьшение движения и читаемость журнала.
- Новых разрешений и runtime-зависимостей нет. Воспроизведение Embed зависит от внешних сервисов; автоматические проверки не заменяют проверку всех живых сайтов и системных папок.

### English

- Recent Downloads grows with visible files up to the bottom of the left statistics column, then scrolls internally. Collapsing groups shrinks the panel without a blank tail. Prevent resize-observer loops when the list changes.
- Fix Instagram Reels action rails, the TikTok profile-modal Copy/Save pair, Tumblr share controls and source-post ownership, and hover access to Twitch clips Copy.
- Recognize e-shuushuu /large/ renditions and recover original lookup when its API is unavailable. Preserve the proven source-post link for VK photos.
- Explicitly acknowledge refused inline requests without a false Downloads admission. Selected post, frame and source checks remain authoritative.
- Retrying an uncertain save checks the existing file through the same confirmation barrier without bypassing a refusal or overwriting the file.
- Skip irrelevant Reel-rail searches in the ordinary Instagram feed, stop stale-speed timers for hidden downloads, and avoid rewriting unchanged preview rows on insertion.
- Reveal the selected section in narrow navigation and keep the settings save bar clear of the edited field. Refine reduced motion and journal readability.
- No new permissions or runtime dependencies. Embed playback depends on external services; automated checks do not establish every live site or external folder grant.

## 3.0.5

Stable GitHub release with a verified owner-signed CRX and matching minified ZIP. Chrome Web Store submission and approval remain separate owner actions.

### Русский

- Добавлены выразительные переходы кнопок, вкладок, меню и popup: световой акцент основных действий, плавный индикатор раздела и появление панелей. Переключатели плавно раскрывают галочку при наведении; уменьшение движения учитывается.
- Сохранение получило единый пример полного пути, раздельный выбор папки и подпапки, прямоугольные уровни с номерами, компактную сетку платформ и прямые действия переноса настроек. Левая навигация и объём сохранённого под меню сохранены.
- Copy первого Shorts не считает ссылку из карусели рекомендаций ссылкой выбранного ролика; конфликт адреса страницы и собственного ID по-прежнему блокирует копирование.
- При прямом открытии Shorts копирование работает и до появления меток активности/начала воспроизведения, если выбранный ролик — единственный преимущественно видимый. Соседние ролики и конфликтующие ID не получают ссылку страницы.
- TikTok и Instagram не запускают полное сканирование разметки из-за смены собственных иконок; TikTok пропускает посторонние мутации. Сохранены восстановление кнопок и очистка переиспользованных карточек; подписка ResizeObserver учитывает раннее сканирование.
- Copy в Instagram требует подтверждённую панель действий поста и не добавляется к одинокому сердцу комментария.
- Имена видео TikTok используют подтверждённый ID выбранного ролика и проверенное расширение файла. Inline и контекстное меню сохраняют прежний точный URL; настройки составных имён продолжают применяться.
- Разбор исходного файла Gelbooru-семейства учитывает ссылку с текстом `Original`, сохраняя проверки домена, пути и хеша.
- Обновлена только dev-зависимость undici в существующем диапазоне jsdom; она не входит в расширение. Актуализированы документация и правила аудита.

### English

- Add expressive button, tab, menu and popup transitions: primary-action light sweep, gliding section indicator and panel arrivals. Choices smoothly reveal a check on hover; reduced motion is respected.
- Give Saving one full-path example, split destination/subfolder controls, indexed rectangular tokens, a compact platform grid and direct settings-transfer actions. Keep left navigation and saved volume below the menu.
- Exclude related-video carousel links from the owning Short's ID; keep owner/page conflicts fail closed when copying the first Short.
- Resolve a directly opened paused Short before native active markers when its renderer is uniquely mostly visible; keep neighboring/hidden/ambiguous owners and conflicting IDs fail closed.
- Port held TikTok/Instagram mutation filters onto current ownership, paired visibility and fullscreen guards; initialize fresh resize subscriptions after early scans.
- Reject lone comment-heart rails for Instagram post Copy.
- Name TikTok video exports by the verified selected-item ID through both entry points, without rewriting the transfer URL or bypassing filename settings.
- Recognize plain `Original` links in the Gelbooru-family parser while preserving domain/path/hash checks.
- Update the development-only undici lock entry and current documentation/audit guidance. Release 3.0.5 validation and exact package identity are recorded in the release provenance.

## 3.0.4

Stable 3.0.4 was published on GitHub. Store upload was owner-reported; Store approval is not established by this changelog.

### Русский

- Добавлена красная тема. Все темы получили подсветку карточек, короткие переходы и фоновую ленту; уменьшение анимации и скрытая вкладка учитываются.
- Превью ссылок: Reddit, Pixiv, Bluesky, Threads, Twitch, Tumblr и Bilibili собраны в компактных группах. Вставленную ссылку можно преобразовать и скопировать без запроса страницы.
- Кнопки копирования на этих площадках используют выбранный сервис превью. В Bluesky, Threads и ленте Tumblr они находятся в панели своего поста, в Pixiv — рядом со скачиванием.
- Исправлены привязка к посту и работа клавиатуры. Bilibili распознаёт локализованные адреса и отличает текущий ролик от рекомендаций; Pixiv сохраняет положение кнопок при прокрутке.
- Inline-кнопки копирования и скачивания скрываются в полноэкранном режиме. Уже запущенная загрузка продолжается.
- Выбранные переключатели стали заметнее; исчезло мигание лишних галочек при смене раздела. Раскрывающиеся пояснения, меню тем и панели настроек выровнены.
- Кнопки VK не перекрывают счётчик галереи. Ошибки и подробности загрузок стали компактнее; лишние постоянные кнопки сохранения настроек убраны.
- Новых разрешений и зависимостей нет. Воспроизведение Embed зависит от внешнего сервиса и мессенджера; стабильная работа каждого зеркала не гарантируется.

- Парные inline-кнопки используют синхронный показ: общий цикл наведения и временная шкала проявления; сохранены управление клавиатурой и постоянно видимые действия в панелях постов.

### English

- Add owner-bound on-site Copy post link controls for Reddit, Pixiv, Bluesky, Threads, Twitch clips/VODs, Tumblr and Bilibili, using saved Link previews. Existing X/Instagram/TikTok/YouTube controls remain. Stale/ambiguous targets fail closed; clipboard denial and unconfirmed fallback remain distinguishable. No new download adapter, clipboard-read permission or background fetch.

- Make selected toggle buttons explicit with a theme-colored double edge and checkmarks for notification duration/folder modes; keep selection distinct from keyboard focus. Empty statistics help no longer grows into an empty outer card.

- Unify explanatory disclosure headers across statistics, routing, local data, settings transfer and debug groups. Update instructions expand from the version-card footer into that card; native keyboard behavior, focus, drafts and existing compact download headers are retained.
- Add a separate Red theme with matching toolbar icons, page notices, early-paint cache and portable settings. Existing saved themes and the Violet default remain valid. All themes share surface hover highlights and a short section-entry transition. The theme picker opens beneath its trigger without clipping its first options at the top of the page.
- Add a theme-colored moving mesh ribbon behind all seven sections of the full page, including Overview and Downloads. Hidden documents pause it; reduced motion keeps it still and forced colors hide it. The background does not intercept input or change download behavior.

- Link previews balances the twelve providers into two groups of six, with TikTok under Media platforms. A compact source/result pair embeds Copy in the result; Reset moves to the page header and rows show their original domains. Clearing the pasted link returns to the local example without changing settings.

- Missing Bluesky, Threads, Tumblr, Twitch and Bilibili marks use bundled vector logos. The Booru family uses a shared local imageboard-grid icon, including the author-folder chip.

- Link previews adds Reddit, Pixiv, Bluesky, Threads, Twitch clips, Tumblr and Bilibili with compact grouped provider rows and a local paste/copy converter. Saved source-copy preferences and portable settings include all seven; VK and existing provider choices are preserved. Twitch VODs remain original links; external playback is not guaranteed. The title help icon is optically centered.

- Saving and Link previews show Save/Discard only for an unsaved draft or an active save. The obsolete idle Save settings footer is removed; explicit persistence, error recovery and keyboard focus are retained.
- VK inline actions move to the upper-right corner of their own media and leave room for native gallery counters/corner buttons. Selected-photo and whole-post proofs remain unchanged.
- Compact download errors and expanded details remove the thumbnail-width left gutter, keep the raw code beside the title and retain the explanation/recovery action. These changes are included in the published 3.0.4 baseline.

- Keep native Threads/Tumblr post actions persistent; bind Pixiv Copy to its proven Download rail with keyboard traversal, and recognize localized Bilibili player routes without borrowing recommendation links.
- Hide inline controls universally during fullscreen and prevent unchecked checkmark flashes during section transitions.
- External Embed playback remains dependent on mirror availability and messenger support.

- Paired inline controls share their hover lifecycle and entry-opacity timeline, preserving keyboard traversal, reduced motion and persistent native post actions.

## 3.0.3 — 2026-10-25

Prepared locally from the accepted roadmap changes. CRX signing and Chrome Web Store upload/review are performed separately by the owner; GitHub publication is not part of local preparation.

### Русский

- Конструктор папок сочетает простой выбор и расширенный интерактивный путь с общей панелью имён/шаблона. Popup возвращён к компактной строке поиска и фильтров. В журнале расширен поиск; в истории версий стрелки стоят рядом, выбор версии отделён, добавлены категории «Все / Новое / Исправления». Карточки сервисов превью больше не растягиваются до соседней; краткая справка сохранена.
- Уведомления получили длительность 2/4/8 секунд или до закрытия и живой локальный тест без загрузок/статистики. Значок папки различает проверенную загрузку браузера и прямую запись в выбранную папку; во втором случае поясняет ограничение API. Companion не возвращается.

- Настройки показывают уровни папок по порядку с перестановкой мышью и клавиатурой, примерами пути и имени рядом с выбором, счётчиком сервисов авторов и плавающей панелью «Сохранить / Отменить». Превью ссылок объединяет независимые настройки YouTube и показывает локальный пример. Улучшены поиск popup, фильтры журнала, пример уведомления и раздел обновлений. Домены, значения по умолчанию и сохранённый выбор остаются прежними.

- Имена папок по умолчанию для новых сохранений: `Image`, `Videos`, `GIF`. Настройки и примеры используют те же значения; собственные имена, уже сохранённые файлы и пути принятых заданий не меняются.
- Для неопределённого результата сохранения появилась команда «Проверить сохранённый файл». Она сверяет уже записанный файл и исправляет результат в истории и статистике только при подтверждении; повторного скачивания или перезаписи нет.
- Reddit: явная метка GIF у выбранного плеера учитывается и кнопкой Save, и ПКМ, даже когда источник имеет формат MP4. Обычные видео не конвертируются; действуют прежние ограничения длительности и размера.
- Instagram: сокращены повторные обходы уже найденных панелей действий. На синтетической ленте из 200 карточек медиана обхода снизилась примерно с 284 до 27 мс; это не замер живого сайта.
- Незавершённые записи статистики переживают перезапуск браузера через компактную приватную очередь; повторная доставка не удваивает счётчики. Отключение записи и границы очистки/восстановления сохраняются.
- Копирование ссылок различает успех, отказ и неподтверждённый результат. Повторное внедрение X, TikTok и YouTube больше не добавляет наблюдатели и глобальные обработчики.

- Узкая вкладка (320–390 px): переключатели темы и языка получили отдельную строку и больше не перекрывают название MediaLatch. Раскладка шире 640 px не менялась; проверка измеряет реальные прямоугольники для RU/EN и всех тем.

- Настройки → Сохранение: для типов изображений (`pic`), видео (`video`) и анимаций (`gif`) можно задать отдельные имена папок. Они заменяют только уровень `{type}`; пустое поле использует Image, Videos или GIF, а неизвестный или не медийный результат по-прежнему идёт в `unknown-type`. Допускается одно имя не длиннее 50 символов без `/`, `\`, `..` и зарезервированных имён; ошибка показана рядом с полем, сохранение требует кнопки «Сохранить», сохранённые файлы не переименовываются. Имена входят в перенос настроек и применяются к обычному пути, выбранной папке и обоим результатам конвертации анимации.

### English

- Folder settings combine Simple and an Advanced interactive path with one names/template panel. Restore compact popup search/types, widen Debug search, separate version selection from adjacent arrows and add All/New/Fixes release categories. Preview service cards keep their own height and concise help.
- Notifications gain 2/4/8-second or until-dismissed duration and a real local test without downloads/statistics. Folder icons distinguish verified native browser downloads from chosen-directory writes; the latter explain the API limitation. No companion is restored.

- Settings now show folder levels in their actual order with drag/keyboard movement, nearby path and filename examples, author selection counts and a sticky explicit Save/Discard bar. Link previews group the independent YouTube choices and show a local example. Popup search, debug filters, notification preview and Updates layouts are more readable. Existing domains, defaults and stored choices remain.

- Default folders for new saves are `Image`, `Videos` and `GIF`. Settings and previews use the same values; explicit custom names, existing files and admitted job paths stay unchanged.
- An uncertain export now offers Check saved file. It checks the already owned result and corrects history/statistics only after confirmation, without another download or overwrite.
- Reddit: an explicit GIF marker on the selected player reaches conversion through Save and the context menu even when the source is MP4. Ordinary videos stay video; existing duration and size limits still apply.
- Instagram: repeated traversal of already reconciled action rails is reduced. A synthetic 200-card feed's median scan fell from about 284 to 27 ms; this is not a live-site measurement.
- Failed statistics writes survive a browser restart through compact private pending records; replay does not double counters. Recording opt-out and clear/restore boundaries remain intact.
- Link copying distinguishes success, refusal and an unconfirmed write. Reinjecting X, TikTok and YouTube no longer adds observers and global listeners.

- Narrow tab (320–390 px): the theme and language controls now take their own row and no longer cover the MediaLatch name. The layout from 640 px up is unchanged; the check measures real rectangles for RU/EN and every theme.

- Settings → Saving: the picture (`pic`), video (`video`) and animation (`gif`) folder labels can be renamed independently. They replace only the `{type}` level; an empty field keeps the standard name, and an unknown or non-media result still uses `unknown-type`. One name only: no `/`, `\`, `..`, reserved names or more than 50 characters. The error appears beside the field, saving needs the explicit Save button, and already saved files are not renamed. The labels are part of portable settings and apply to the normal browser path, a selected folder and both animation conversion outputs.

## 3.0.2 — 2026-10-24

Prepared locally on 2026-10-24. These changes are not in the published 3.0.1 package. Local packaging, owner CRX signing, GitHub publication and store review are separate steps.

### Русский

- Пересборка 3.0.2 от 2026-10-25. Проверка обновлений различает обычный HTTP 403 и подтверждённый лимит GitHub. Пауза сервера сохраняется между открытиями и каналами, блокирует частые ручные повторы и показывает время следующей попытки. Ошибки больше не подавляют автоматическую проверку на сутки; последний успешный результат сохраняется.

- Импорт истории отклоняет нестроковые идентификаторы; повреждённый JSON больше не создаёт дубликаты и неудаляемые записи.

- Исправлена кнопка Copy на страницах Instagram с фотографиями и вертикальной раскладкой без `<article>`. X и обычная кнопка Instagram получили видимый клавиатурный фокус.
- Имя автора VK больше не включает текст вложенной кнопки «Подписаться». RedGIFs ищет аккаунт в своей карточке с одним видео, а не только во внутренней обёртке плеера.
- Inline-сохранение показывает обработку запроса, отказ связи и необходимость перезагрузить страницу после обновления расширения. Ответ фонового процесса не обозначает успешное сохранение файла; итог остаётся в менеджере загрузок.
- При составных именах файлы одного подтверждённого альбома получают индекс `_001`, `_002` и далее в порядке поста. Режим исходного имени и защита от перезаписи сохранены.
- Убрано автоматическое распознавание Scatbooru как рабочего Booru-домена после обнаруженного перенаправления. Исторические записи и счётчики этого сайта сохраняются.
- Кнопка копирования на X привязывается к панели штатных действий поста, а не к первой группе элементов: опросы и вложенные цитаты исключены. При неоднозначной панели кнопка скрывается до восстановления привязки.
- Inline-кнопки X, Instagram, TikTok и YouTube проверяют своё происхождение и текущее место крепления; лишние и клонированные элементы удаляются. Общий обработчик сохранения X, Reddit, Pixiv, VK и e-shuushuu отклоняет нажатия после переноса или удаления контейнера кнопки.
- Добавлены отдельные JSON-копии статистики и завершённой истории загрузок. Восстановление статистики заменяет счётчики с подтверждением, сохраняет настройку записи и исключает повторный учёт старых запросов; при активных загрузках оно запрещено.
- Импорт истории добавляет отсутствующие записи без запуска загрузок, изменения статистики или доступа к файлам. Копия не содержит медиа, превью, URL источников, прав на папки и нативных ID загрузок. Лимиты: 32 МиБ UTF-8 и до 50 000 записей истории.
- Кэш увеличен до 2 048 миниатюр и 256 оригиналов: до 128 МиБ на оригинал, 512 МиБ суммарно и 30 дней доступности. Это кэш, а не резервная копия сохранённых файлов.
- Длинная история отображается порциями с сохранением целых постов, активных записей, фокуса и порядка от фонового процесса. Поиск и массовые действия охватывают весь сохранённый список.
- Новых разрешений и зависимостей нет. При сбое записи прежние данные сохраняются. Ручная приёмка Reload, реальных папок и физического дефицита места остаётся открытой.

### English

- Rebuilt 3.0.2 on 2026-10-25. Update checks distinguish ordinary HTTP 403 from confirmed GitHub rate limits. A persisted server cooldown survives page/channel changes, blocks rapid manual retries and shows the next permitted check time. Failures no longer suppress automatic checks for a day; the previous successful result is retained.

- Reject non-string history identifiers; malformed JSON can no longer create duplicate or unremovable archive records.

- Fix Copy on Instagram photo permalinks with column layouts and no `<article>`. Add visible keyboard focus to X and standard Instagram Copy controls.
- Exclude nested Subscribe controls from VK author names. Resolve RedGIFs account metadata from its own single-video card instead of only the inner player wrapper.
- Show inline request processing, transport failure and page-reload recovery after extension updates. A worker reply does not claim a completed file; Downloads remains the outcome authority.
- Preserve proven album order with `_001`, `_002` and subsequent indexes in metadata-based filenames. Original-name mode and collision protection remain unchanged.
- Retire automatic Scatbooru domain recognition after observed redirection, retaining its historical records and counters.
- Bind the X copy control to the post's native action bar rather than its first group, excluding polls and nested quotes. An ambiguous action bar hides the control until its binding can be established again.
- X, Instagram, TikTok and YouTube inline controls validate their private identity and current anchor; remove surplus and cloned elements. The shared X, Reddit, Pixiv, VK and e-shuushuu Save handler refuses activation after its control host is moved or detached.
- Add separate JSON copies for aggregate statistics and terminal download history. Confirmed statistics restore replaces counters, preserves recording preference and fences old replays; active work refuses restore.
- History import adds missing metadata-only records without downloads, statistics updates or filesystem authority. Copies exclude media, previews, source URLs, folder grants and native download IDs. Limits: 32 MiB UTF-8 and up to 50,000 history records.
- Increase disposable caches to 2,048 thumbnails and 256 originals: 128 MiB per original, 512 MiB total and 30-day availability. Saved files are not backed up by this cache.
- Window long history while keeping whole posts, active/focused records and producer order. Search and bulk actions retain full-list scope.
- No new permissions/dependencies. Failed writes preserve prior data. Actual Reload, external-folder and physical low-space acceptance remain open.


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

## 3.0.0 — License and distribution

### Русский

- Собственный код и графика с версии 3.0.0 распространяются по закрытой лицензии. Ранее полученные GPL-версии сохраняют прежние права; лицензии сторонних компонентов не меняются.
- Чистая сборка подготовлена для ручной упаковки в CRX. Закрытый ключ подписи хранится у владельца и не публикуется. CRX не скрывает JavaScript и не гарантирует установку вне магазина в Chrome для Windows/macOS.
- Сохранены возможности 2.6.5, включая превью изображений/GIF/MP4, карусель, имена файлов, фильтры типов и офлайн-историю изменений. Новых разрешений, зависимостей или изменений формата локальных данных нет. UI собирается текущим Vite с минификацией и без sourcemaps.
- Кодирование GIF перенесено в отдельный Worker: тяжёлая обработка кадров больше не блокирует основной поток скрытого документа. Сохранены результат кодирования, ограничения, отмена и очистка ресурсов.
- Публикация в Chrome Web Store выполняется отдельно. При включённых Verified CRX Uploads магазин принимает CRX, подписанный зарегистрированным ключом; обычный режим использует ZIP.

### English

- Project-owned code and artwork use a proprietary license starting with 3.0.0. Earlier GPL recipients retain their existing rights; third-party licenses are unchanged.
- A clean runtime is prepared for manual CRX packaging. The owner keeps the private signing key outside published artifacts. A CRX does not conceal JavaScript or guarantee installation outside the store in Chrome for Windows/macOS.
- Retains 2.6.5 behavior, including image/GIF/MP4 previews, carousel, filename settings, file-type filters and offline release history. No new permissions, dependencies or local-data format changes. The UI uses the current Vite build with minification and no sourcemaps.
- GIF encoding runs in a dedicated Worker, keeping heavy frame processing off the hidden document's main thread. Encoding output, limits, cancellation and resource cleanup are preserved.
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
- Update EN/RU documentation and privacy disclosures, and separate implemented extraction/MV3 safeguards from future universal-media work in [the architecture roadmap](docs/ROADMAP.md). No new permission, dependency or storage schema.

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

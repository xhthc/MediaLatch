# Структура папок и имена / Folder layouts and filenames

## Русский

В разделе «Сохранение» единый итоговый путь показывает пример для новых файлов: папку назначения, подпапку, уровни структуры и имя. «Загрузки» используют расположение загрузок браузера; свою папку выбирайте отдельной кнопкой. Браузер может запрещать выбор системных папок через диалог — для загрузок используйте кнопку «Использовать Загрузки».

Простая и расширенная настройка используют один черновик. Нажимайте уровни в нужном порядке; выбранные уровни получают номера. При наведении на выключенный пункт появляется полупрозрачная галочка. В расширенном режиме уровни можно перетаскивать, менять через Alt+←/→ и удалять. «Имена папок и шаблон» открывает общие названия сайтов/типов и текстовый шаблон. Платформы авторов включаются отдельно; неизвестный аккаунт не подставляется из соседнего поста.

Шаблоны поддерживают `{site}`, `{author}`, `{type}`, `{ext}`, `{date}`, `{month}`, `{year}`. Названия типов по умолчанию — `Image`, `Videos`, `GIF`; их можно изменить. Дата структуры папок использует UTC: подтверждённое время поста, иначе фиксированное время операции. Составное имя файла использует только подтверждённые метаданные; неизвестные части пропускаются. Файлы альбома сохраняют индекс, совпадающие имена получают номер.

Проверьте пример и нажмите общую кнопку сохранения. «Отменить изменения» возвращает сохранённые значения. Настройки не перемещают и не переименовывают существующие файлы. Экспорт JSON переносит настройки; импорт сначала показывает изменения и требует явного применения. Разрешения папок, медиа и история этим JSON не передаются.

## English

Saving has one resolved new-file example: destination, subfolder, ordered levels and filename. Downloads uses the browser's download location; choose a custom folder through its separate action. The browser can refuse system folders in the picker; use the explicit Use Downloads control for that destination.

Simple and Advanced share one draft. Select levels in nesting order; selected levels show ordinal badges, while inactive options reveal a translucent hover check. Advanced supports drag, Alt+Left/Right reorder and removal. Folder names and template opens the shared site/type-name and template editor. Author platforms are independent opt-ins; unknown accounts are not guessed from nearby posts.

Supported levels: `{site}`, `{author}`, `{type}`, `{ext}`, `{date}`, `{month}`, `{year}`. Default type names are `Image`, `Videos`, `GIF` and can be changed. Folder dates use UTC and confirmed post time when available, otherwise the operation's fixed creation time. Composed filenames use confirmed metadata only; unknown parts are omitted. Albums retain page indices and matching names receive a collision number.

Review the example, then use Save. Discard restores saved values. Settings never move or rename existing files. JSON export transfers settings; import previews changes and requires explicit Apply. That file grants no folder access and carries no media or download history.

[Status](STATUS.md) · [Local data](LOCAL_DATA.md) · [Privacy](PRIVACY.md)

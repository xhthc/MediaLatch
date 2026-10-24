# Состояние проекта / Project status

Обновлено / Updated: 2026-10-24.

| Пакет / Build | Статус / Status |
| --- | --- |
| [3.0.1](https://github.com/xhthc/MediaLatch/releases/tag/v3.0.1) | Стабильный опубликованный runtime: CRX и ZIP с одинаковыми 98 файлами / Stable published runtime: CRX and ZIP contain the same 98 files |
| Следующая версия / Next version | Номер не назначен; локальные изменения проверены, но не выпущены / No version assigned; reviewed local changes are unreleased |
| Chrome Web Store | Отдельный канал публикации; подтверждённая ссылка магазина здесь ещё не указана / Separate distribution channel; a verified listing URL is not yet supplied here |

## Русский

3.0.1 включает компактные шаблоны подпапок, восстановление доступа к выбранной папке, исправления составных имён, изображений RedGIFs и интерфейса. Отдельный Worker кодирования GIF сохранён из 3.0.0. Сохранение в свою папку и локальный просмотр работают без Explorer companion.

Кэш 3.0.1: 128 миниатюр; 16 оригиналов, 64 МиБ на файл, 128 МиБ суммарно и до 24 часов доступности. JSON-восстановления статистики/истории в этом пакете нет.

В локальной разработке проверены отдельные JSON-копии статистики/истории, 2 048 миниатюр, 256 оригиналов с бюджетом 512 МиБ/30 дней и порционная история с целыми постами. Эти функции ещё не опубликованы. Копии содержат сведения, а не медиафайлы; восстановление истории не даёт доступа к файлам и не запускает загрузки.

Далее нужны проверки реального Reload, прав на пользовательскую папку, перезапуска во время активного экспорта и физического дефицита места. Изолированные стенды не подтверждают все сайты с авторизацией и устройства.

## English

3.0.1 includes compact ordered folder templates, saved-folder access recovery, composed-name/RedGIFs-image fixes and UI corrections. The dedicated GIF encoder Worker from 3.0.0 remains. Chosen-folder saving and local preview require no Explorer companion.

3.0.1 cache: 128 thumbnails; 16 originals, 64 MiB per file, 128 MiB total and up to 24-hour availability. Statistics/history JSON restore is not included.

Reviewed local development adds separate JSON statistics/history copies, 2,048 thumbnails, 256 originals with a 512 MiB/30-day budget and history windowing that keeps complete posts. These features are not published. Copies contain metadata, not media; imported history grants no file access and starts no download.

Remaining acceptance includes actual extension-manager Reload, external folder grants, restart during active export and physical storage pressure. Isolated fixtures do not establish every signed-in site or device.

[Roadmap](ROADMAP.md) · [Local data](LOCAL_DATA.md) · [Changelog](../CHANGELOG.md) · [Privacy](PRIVACY.md)

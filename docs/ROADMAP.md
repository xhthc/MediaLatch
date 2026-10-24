# Roadmap

Updated 2026-10-25. Release build: 3.0.2. Acceptance limits are tracked separately in [Status](STATUS.md); this roadmap promises neither dates nor universal site coverage.

## Русский

| Приоритет | Работа |
| --- | --- |
| P1 | Проверить сохранность данных и прав на папку после Reload, перезапуск во время активного экспорта, неопределённый результат записи и отложенную статистику |
| P1 | Проверить реальные пользовательские папки и физический дефицит места отдельно от искусственных сбоев хранилища |
| P2 | Исправлять воспроизводимые пробелы выбора медиа, метаданных и конкретных источников, сохраняя принадлежность выбранному посту и подписанные ссылки |
| P2 | Расширять проверки сайтов с авторизацией, звука, вёрстки, ссылок аккаунтов и буфера обмена |
| P3 | Измерить стоимость SPA-наблюдателей и затем улучшать прокрутку, повторную инициализацию и переработанные карточки |
| Отдельная задача | Добавлять потоковые форматы только для названного сервиса с проверенными плеером, кодеками, звуком и ограничениями |

JSON-копии статистики/истории, увеличенный кэш и порционная история входят в 3.0.2; ручные проверки выше остаются открытыми. Свои отдельные названия для pic/video/gif пока не реализованы. Скачивание YouTube, DRM, эфиры, универсальные HLS/DASH и системный помощник не заявляются.

## English

| Priority | Work |
| --- | --- |
| P1 | Verify Reload data/folder continuity, restart during active export, uncertain writes and pending statistics |
| P1 | Check real destination folders and physical low-space behavior separately from injected storage faults |
| P2 | Fix reproduced selected-media/metadata/provider gaps while retaining ownership proof and exact signed URLs |
| P2 | Extend signed-in site, audio/layout, account-link and clipboard acceptance |
| P3 | Measure SPA observer cost before changing scroll/reinjection/recycled-card handling |
| Separate capability | Add streams only for a named provider with proven player/codec/audio and resource bounds |

JSON statistics/history copies, a larger cache and history windowing are included in 3.0.2; the manual acceptance tasks above remain open. Per-type pic/video/gif naming is not implemented. YouTube downloading, DRM, live streams, universal HLS/DASH and a system companion are not promised.

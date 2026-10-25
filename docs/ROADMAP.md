# Roadmap

Updated 2026-10-25 for release 3.0.3. Acceptance limits are separate from implementation in [Status](STATUS.md); no dates or universal site coverage are promised.

## Русский

В 3.0.3 реализованы свои названия Image/Videos/GIF, простой/расширенный конструктор, восстановление ожидающей статистики, проверка неопределённого сохранения, Reddit GIF и улучшения интерфейса/SPA. JSON-копии истории/статистики, увеличенный кэш и поиск по сохранённой истории сохранены из 3.0.2. Эти пункты не нужно реализовывать повторно.

| Приоритет | Работа |
| --- | --- |
| P1, ручная приёмка | Реальная папка Windows: выбор, отмена, доступ после Reload/перезапуска и восстановление. Владелец сообщает успешную первую проверку; это не универсальная гарантия разрешений |
| P1, отдельный стенд | Физический дефицит места и естественное вытеснение; искусственные API-сбои уже покрыты отдельно. Не заполнять рабочий диск пользователя |
| P2 | Reddit GIF через кнопку и ПКМ, RedGIFs Trending/коллажи, авторизованные ленты, звук, выбранный пост/автор и буфер обмена |
| P2, по воспроизведению | Пробелы выбора медиа/метаданных/источников: точная ссылка и принадлежность выбранному посту до расширения обработчика |
| P3 | Измерения живых SPA-лент и производительности на устройстве; изолированные профили не доказывают FPS пользователя |
| Отдельная задача | Потоковый адаптер для названного сервиса с проверенными плеером, кодеками, звуком и ресурсными границами |

Изолированные проверки Reload, полного перезапуска экспорта, неопределённой записи и ожидающей статистики выполнены; они не заменяют реальные разрешения Windows и все сайты. Скачивание YouTube, DRM, эфиры, универсальные HLS/DASH и системный помощник не заявлены. Firefox, архивы авторов и автоматизация магазина остаются отдельными задачами.

## English

Release3.0.3 implements custom Image/Videos/GIF labels, simple/advanced folder controls, pending-statistics recovery, uncertain saved-result checks, Reddit GIF classification and UI/SPA improvements. JSON copies, larger caches and retained-history search remain from3.0.2; do not queue duplicate implementation.

| Priority | Work |
| --- | --- |
| P1, manual | Real Windows folder selection/cancellation and grant recovery across Reload/restart. The owner reports the first manual item works; this is not a universal grant guarantee |
| P1, separate test device | Physical low space/natural eviction; API faults are separate coverage. Do not fill the user's working disk |
| P2 | Reddit GIF via inline/context menu, RedGIFs Trending/collages, signed-in feeds, audio, selected post/account and clipboard |
| P2, reproduced targets | Exact selected-media/metadata/provider failures before broadening discovery |
| P3 | Live-feed/device performance measurements; isolated profiles do not prove user hardware FPS |
| Separate capability | A named stream provider with proven player/codec/audio and resource bounds |

Isolated manager Reload, full export restart, uncertain directory-close and pending-statistics cases are covered separately from actual Windows permissions and all-site acceptance. YouTube downloading, DRM, live streams, universal HLS/DASH and a system companion are not promised. Firefox, author archives and Store automation remain separate assignments.

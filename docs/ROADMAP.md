# Roadmap

Updated 2026-10-27 for release 3.0.5. Acceptance limits are separate from implementation in [Status](STATUS.md); no dates or universal site coverage are promised.

## Русский

В 3.0.5 завершены новый раздел сохранения с единым итоговым путём, порядковые уровни, галочки при наведении, сетка авторов, прямой перенос JSON и переходы интерфейса. Исправлены Shorts при первом открытии, панели Instagram, имена TikTok и разбор оригиналов Gelbooru. Эти функции не нужно реализовывать повторно; ручная приёмка ниже остаётся отдельной.

В 3.0.4 реализованы красная тема и анимации для всех тем, компактные настройки 12 превью, Copy на новых площадках, синхронный показ парных кнопок, защита полноэкранного режима и исправления привязки/клавиатуры. Владелец сообщает успешные проверки сервисов; доступность внешних зеркал и меняющаяся вёрстка сайтов остаются отдельной приёмкой.

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

Release 3.0.5 implements unified Saving output, ordered controls, hover checks, the author grid, direct JSON transfer and interface motion. First-Short Copy, Instagram action rails, TikTok names and Gelbooru originals are fixed. Do not queue these implementations again; manual acceptance below remains separate.

Release 3.0.4 implements the Red theme and motion across themes,12 compact preview settings, Copy on additional sites, paired reveal synchronization, fullscreen suppression and ownership/keyboard fixes. The owner reports working service checks; external mirror availability and changing site layouts remain separate acceptance.

Release 3.0.3 implements custom Image/Videos/GIF labels, simple/advanced folder controls, pending-statistics recovery, uncertain saved-result checks, Reddit GIF classification and UI/SPA improvements. JSON copies, larger caches and retained-history search remain from 3.0.2; do not queue duplicate implementation.

| Priority | Work |
| --- | --- |
| P1, manual | Real Windows folder selection/cancellation and grant recovery across Reload/restart. The owner reports the first manual item works; this is not a universal grant guarantee |
| P1, separate test device | Physical low space/natural eviction; API faults are separate coverage. Do not fill the user's working disk |
| P2 | Reddit GIF via inline/context menu, RedGIFs Trending/collages, signed-in feeds, audio, selected post/account and clipboard |
| P2, reproduced targets | Exact selected-media/metadata/provider failures before broadening discovery |
| P3 | Live-feed/device performance measurements; isolated profiles do not prove user hardware FPS |
| Separate capability | A named stream provider with proven player/codec/audio and resource bounds |

Isolated manager Reload, full export restart, uncertain directory-close and pending-statistics cases are covered separately from actual Windows permissions and all-site acceptance. YouTube downloading, DRM, live streams, universal HLS/DASH and a system companion are not promised. Firefox, author archives and Store automation remain separate assignments.

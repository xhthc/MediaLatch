# Security Policy / Политика безопасности

[Русский](#русский) · [English](#english)

## Русский

### Поддерживаемые версии

Исправления ориентированы на последний стабильный выпуск — 3.0.1. Отдельное сопровождение старых веток не обещается.

### Сообщить об уязвимости

О багах, проблемах и уязвимостях сообщайте одним из способов:

- Email: [always1337@vk.com](mailto:always1337@vk.com), тема `MediaLatch security`.
- Issues: [xhthc/MediaLatch](https://github.com/xhthc/MediaLatch/issues).

Не публикуйте действующий эксплойт или чувствительные данные в Issues. Подробности уязвимости отправляйте на почту.

Укажите версию расширения, браузер/ОС, минимальные шаги воспроизведения, ожидаемый и фактический результат, возможное влияние. Прикладывайте обезличенный пример или короткий PoC. Не отправляйте cookies, токены, закрытые ключи, подписанные ссылки, приватные файлы или полный необработанный Debug-отчёт; при необходимости сначала согласуйте способ передачи чувствительных данных.

### Границы проверки

Особенно полезны сообщения о переходе границ между страницей и расширением, неверной авторизации привилегированных сообщений, утечке локальных данных, обходе проверки URL/редиректов, путей и типов файлов, непреднамеренной перезаписи и выполнении непроверенного кода. Ошибки сохранения и интерфейса без влияния на безопасность можно отправлять в обычные Issues.

Проверяйте на собственном профиле и тестовых данных. Не затрагивайте чужие аккаунты, файлы или инфраструктуру. Уязвимости самого Chromium и сторонних сервисов направляйте их владельцам; если проблема затрагивает интеграцию MediaLatch, укажите это в сообщении.

### Разбор и раскрытие

Сообщения разбираются вручную. Фиксированные сроки ответа или выпуска исправления не гарантируются. Порядок публичного раскрытия и упоминание автора согласуются отдельно. Наличие этой политики не означает, что код прошёл сертификацию безопасности или что включена форма GitHub Private Vulnerability Reporting.

## English

### Supported versions

Fixes target the latest stable release, 3.0.1. Separate maintenance of older branches is not promised.

### Report a vulnerability

Report bugs, problems and vulnerabilities through either channel:

- Email: [always1337@vk.com](mailto:always1337@vk.com), subject `MediaLatch security`.
- Issues: [xhthc/MediaLatch](https://github.com/xhthc/MediaLatch/issues).

Do not post a working exploit or sensitive data in public Issues. Send vulnerability details by email.

Include the extension version, browser/OS, minimal reproduction steps, expected and actual behavior, and potential impact. Use a redacted fixture or small proof of concept. Do not send cookies, tokens, private keys, signed URLs, private files or an unreviewed raw Debug export. Agree on a suitable transfer method first if sensitive evidence is necessary.

### Testing scope

Useful reports include page-to-extension trust-boundary failures, unauthorized privileged messages, local-data disclosure, URL/redirect/path/type-check bypasses, unintended overwrites and execution of untrusted code. Ordinary saving or UI bugs without security impact can go to Issues.

Test with your own profile and fixtures. Do not affect other people's accounts, files or infrastructure. Report Chromium and third-party service vulnerabilities to their maintainers; describe any MediaLatch integration impact separately.

### Triage and disclosure

Reports are reviewed manually. No fixed response or patch deadline is guaranteed. Public disclosure and reporter credit are agreed separately. This policy is not a security certification and does not imply that GitHub Private Vulnerability Reporting is enabled.

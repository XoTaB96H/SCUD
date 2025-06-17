# SCUD — Система контроля и уравление доступом для малых предприятий

> Open‑source hardware & software access‑control suite

**SCUD** — открытая система контроля и управления доступом (СКУД), разработанная в рамках магистерской работы для потребностей небольших предприятий. Комплекс состоит из трёх взаимосвязанных подсистем, каждая из которых публикуется в отдельном репозитории.

## Репозитории

| Подсистема                    | Репозиторий                                                                                   | Назначение                                                                                                 |
| ----------------------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Веб‑панель администратора     | [https://github.com/XoTaB96H/SCUD-admin](https://github.com/ORG_NAME/SCUD-admin)       | Django backend + React/Tailwind UI; управление пользователями, расписаниями и точками доступа; REST API.   |
| Мобильное приложение GatePass | [https://github.com/XoTaB96H/SCUD-mobile](https://github.com/ORG_NAME/SCUD-mobile)     | Android (Kotlin). NFC/BLE «цифровой пропуск», оффлайн‑токены Ed25519, push‑уведомления о проходах.         |
| Прошивка считывателя          | [https://github.com/XoTaB96H/SCUD-firmware](https://github.com/ORG_NAME/SCUD-firmware) | ESP32‑C6 + FreeRTOS. RFID/NFC, TLS 1.3‑защищённый канал с сервером, управление реле замка, OTA‑обновления. |



## Ключевые особенности

* **Открытая аппаратная платформа** — модульный считыватель на ESP32‑C6, поддержка дополнительных RFID/NFC‑антенн.
* **Защищённый обмен данными** — взаимная TLS‑аутентификация, AES‑GCM‑шифрование, подписи Ed25519.
* **Оффлайн‑режим** — локальная валидация короткоживущих токенов при потере связи с сервером.
* **Низкая стоимость внедрения** — массовые компоненты и полностью свободное программное обеспечение.
* **Импортозамещение** — исходники и схемы открыты для перехода на отечественные микроконтроллеры.

## Быстрый старт

1. **Разверните сервер**: следуйте инструкциям в `SCUD-admin` (Docker Compose, `.env` для БД).
2. **Соберите и прошейте считыватель**: инструкции в `SCUD-firmware`, укажите адрес сервера в конфигурации `sdkconfig`.
3. **Установите мобильное приложение**: скачайте `apk` из релизов `SCUD-mobile`, отсканируйте QR‑код регистрации из веб‑панели.

Подробные руководства и схемы приведены в README каждого репозитория.

## Лицензия

* Программный код — MIT License
* Аппаратная документация (схемы, платы) — CERN‑OHL‑P v2

---

# SCUD — Open Access Control Suite for SMEs

*SCUD* is an open‑source access‑control system aimed at small enterprises. It is split into three repositories:

| Sub‑system          | Repository                                                                                    | Purpose                                                                                 |
| ------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Admin Web Panel     | [https://github.com/XoTaB96H/SCUD-admin](https://github.com/ORG_NAME/SCUD-admin)       | Django backend, React/Tailwind UI, REST API, event log, access rule editor.             |
| GatePass Mobile App | [https://github.com/XoTaB96H/SCUD-mobile](https://github.com/ORG_NAME/SCUD-mobile)     | Android digital pass (NFC/BLE), offline Ed25519 tokens, push notifications.             |
| Reader Firmware     | [https://github.com/XoTaB96H/SCUD-firmware](https://github.com/ORG_NAME/SCUD-firmware) | ESP32‑C6 firmware, RFID/NFC reader, TLS 1.3 secure channel, relay control, OTA updates. |

See individual READMEs for installation and contribution guidelines.

Licensed under **MIT** (software) and **CERN‑OHL‑P v2** (hardware).

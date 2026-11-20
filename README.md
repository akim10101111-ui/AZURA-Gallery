# AZURA Gallery

Нативная Android-галерея для фотографий и видео с локальным хранением.

## Открыть в Android Studio

1. Скачайте и распакуйте проект целиком.
2. Откройте в Android Studio папку, в которой лежат `settings.gradle.kts` и `gradlew`.
3. Дождитесь Gradle Sync. Нужны JDK 17 и Android SDK Platform 34 / Build Tools 34.0.0.
4. Для сборки тестовой версии выберите `app` → `Tasks` → `build` → `assembleDebug` или выполните `./gradlew assembleDebug`.
5. Debug APK появится в `app/build/outputs/apk/debug/app-debug.apk`.

## Параметры проекта

- Application ID: `com.azura.gallery`
- Namespace: `com.azura.gallery`
- Минимальная версия Android: 10 (API 29)
- Target SDK: 34
- Версия проекта: 1.2.0 (versionCode 5)
- JDK: 17
- Проект не запрашивает `INTERNET` permission; внешние ссылки в блоке контактов открываются системным браузером/приложением, если оно установлено.

## Подпись Release

Debug APK подписывается тестовым debug-сертификатом и предназначен для установки и проверки. Для публикации нужен постоянный собственный ключ подписи. Не используйте debug-ключ как ключ публикации и не теряйте исходный keystore.

В корне проекта предусмотрен `keystore.properties` (он исключён из Git). Заполните его локально данными своего keystore по образцу `keystore.properties.example`; файл keystore и пароли не отправляйте в репозиторий и не передавайте посторонним. Затем соберите `./gradlew assembleRelease bundleRelease`. Без `keystore.properties` release APK/AAB будет не подписан.

## Проверки

Перед выпуском выполните `./gradlew clean testDebugUnitTest lintDebug assembleDebug assembleRelease bundleRelease`. Автоматические проверки не заменяют тест на физических телефонах: отдельно проверьте разрешения к фото/видео, просмотр больших библиотек, видео, редактор и сохранение копии, альбомы, избранное, удаление/восстановление, поиск и поведение при отказе в разрешениях.

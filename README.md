# Gallery

Нативная Android-галерея для фотографий и видео с локальным хранением.

## Открыть в Android Studio

1. Скачайте и распакуйте проект целиком.
2. Откройте папку, где лежат `settings.gradle.kts` и `gradlew`.
3. Дождитесь Gradle Sync. Нужны JDK 17 и Android SDK Platform 34 / Build Tools 34.0.0.
4. Для сборки тестовой версии выберите `app` → `Tasks` → `build` → `assembleDebug` или выполните `./gradlew assembleDebug`.
5. Debug APK появится в `app/build/outputs/apk/debug/app-debug.apk`.

## Параметры проекта

- Application ID: `com.azura.gallery` (внутренний ID)
- Namespace: `com.azura.gallery`
- Минимальная версия Android: 10 (API 29)
- Target SDK: 34
- Версия проекта: 1.2.0 (versionCode 5)
- JDK: 17
- Приложение работает офлайн и не запрашивает `INTERNET` permission.

## Подпись Release

Debug APK подписывается тестовым debug-сертификатом и предназначен для установки и проверки. Для публикации нужен собственный постоянный ключ подписи. Не используйте debug-ключ как ключ публикации и храните keystore в безопасном месте.


Build verification is enforced in the GitHub Actions workflow after changes to the project files.

CI build triggered to validate vector resource and display-name changes.

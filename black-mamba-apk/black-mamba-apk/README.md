# Black Mamba: сборка APK

В папке `www` лежит сама игра (один файл `index.html`). Проект собирает из неё Android-приложение через Capacitor.

## Способ 1. Бесплатная сборка на GitHub (ничего не нужно устанавливать)

1. Зарегистрируйся на github.com и создай новый репозиторий (кнопка New).
2. Загрузи в него всё содержимое этой папки: Add file, Upload files. Проще с компьютера: перетащи папки `www` и `.github` и файлы `package.json`, `capacitor.config.json`.
   Если папка `.github` не загрузилась, создай файл вручную: Add file, Create new file, в имени напиши `.github/workflows/build-apk.yml` и вставь содержимое файла из этой папки.
3. Открой вкладку Actions. Выбери Build APK и нажми Run workflow. Сборка идёт 5-10 минут.
4. Открой завершённый запуск. Внизу в разделе Artifacts скачай `black-mamba-apk`. Внутри zip лежит `app-debug.apk`.
5. Перенеси APK на телефон и открой его. Android попросит разрешить установку из неизвестных источников, разреши.

## Способ 2. Android Studio на компьютере

Нужны Node.js 20 и Android Studio.

    npm install
    npx cap add android
    npx cap sync android
    npx cap open android

В Android Studio: Build, Build Bundle(s) / APK(s), Build APK(s).

## Заметки

- Это отладочный APK для установки у себя. Для публикации в Google Play нужна подписанная release-сборка.
- Шрифты подгружаются из интернета. Без сети игра работает на системных шрифтах.
- Название приложения меняется в `capacitor.config.json` (appName).

# 📺 Smart TV Portal (Hisense Edition)

> **Cloud-Based Smart TV Portal & IPTV Playlist for Media Station X (MSX), VIDAA OS, and Lampa.**

---

## 🚀 Настройка на телевизоре Hisense (VIDAA OS) и Smart TV

### 1. Установка Media Station X (MSX)
1. В телевизоре откройте магазин приложений (**VIDAA App Store** или аналог на WebOS/Tizen/Android TV).
2. Найдите и установите **Media Station X** (MSX).

### 2. Установка стартового параметра
1. Запустите **Media Station X**.
2. Перейдите в меню: **Settings (Настройки)** ➔ **Start Parameter (Стартовый параметр)** ➔ **Setup (Настроить)**.
3. Введите адрес стартового файла:
   ```text
   https://raw.githubusercontent.com/vovamalina19742-ru/smart-tv-portal/main/msx.json
   ```
4. Подтвердите ввод (галочка / OK).
5. Приложение загрузит интерфейс портала со всеми категориями и кнопкой запуска **Lampa**.

---

## 📂 Архитектура портала (MSX Standard)

Портал построен по официальному стандарту Media Station X:
* `msx.json` — стартовый файл конфигурации с параметром `"parameter": "menu:https://.../menu.json"`.
* `menu.json` — главное навигационное меню (иконки, баннеры, ссылки на категории).
* `federal.json` — эфирные и федеральные телеканалы.
* `cinema.json` — кино, сериалы и премиальные каналы.
* `sports.json` — спортивные трансляции и матчи.
* `discovery.json` — познавательные каналы и документалистика.
* `kids_music.json` — мультфильмы, детские каналы и музыкальные клипы.
* `lampa.json` — страница запуска веб-кинотеатра Lampa (`action: "link:..."`).
* `assets/` — локальные логотипы и графические ресурсы портала.

---

## 📜 Плейлист M3U8 (для TiviMate, OTT Navigator, Televizo)

Нормализованный M3U8-плейлист с телепрограммой (EPG):
```text
https://raw.githubusercontent.com/vovamalina19742-ru/smart-tv-portal/main/playlist.m3u8
```

Особенности плейлиста:
* Стандартные LF (`\n`) переводы строк (корректно читается строгими плеерами).
* Встроенный заголовок EPG: `url-tvg="http://epg.it999.ru/edem.xml.gz,https://iptv-org.github.io/epg/guides/ru/ntvplus.ru.epg.xml"`.
* Все ссылки проверены на доступность, мертвые потоки отфильтрованы.
* Группировка каналов по категориям (`group-title`).

> [!NOTE]
> Публичные IPTV-потоки могут периодически менять токены или отключаться источниками вещания. Рекомендуется периодически обновлять список активных потоков.

---

## 📄 Лицензия

Проект распространяется под свободной лицензией [MIT](LICENSE).

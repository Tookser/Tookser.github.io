+++
title = "Автозапуск обсидиана, горячие клавиши для обсидиана, нахождение обсидиана в трее."
date = "2025-04-14T19:25:55+03:00"
author = "Иван"
cover = ""
tags = ["obsidian", "linux", "ubuntu"]
keywords = ["obsidian tray", "значок obsidian на панели задач"]
description = "Настройки Обсидиана для того, чтобы проще к нему обращаться"
showFullContent = false
readingTime = true
draft = false
+++

Мой конфиг [Obsidian tray](https://github.com/dragonwocky/obsidian-tray) плагина (позволяет убирать Обсидиан в значок на панели задач). Ubuntu 22.04 LTS.

![Фото конфигурации](obsidian_tray_config.jpg)

1-я галочка (автозапуск) почему-то не работает, поэтому сделал автозапуск через добавление .desktop файла в
`~/.config/autostart` , а галочку снял от греха подальше.

`winkey` в горячей клавише не получилось внедрить — пользуюсь `ctrl+shift+o` по умолчанию.

Сейчас работает **так**: при закрытии убирается в трей, по горячей клавише/клике на значок возвращает. Можно свернуть окно — тогда не убирает в трей, удобно, если хочется подвигать мышкой.

Daily note — не пользуюсь просто.

то же, но файлом `data.json` (`trayIconImage` тоже можно поменять):

```json
{
  "launchOnStartup": false,
  "hideOnLaunch": true,
  "runInBackground": true,
  "hideTaskbarIcon": false,
  "createTrayIcon": true,
  "trayIconImage": ...,
  "trayIconTooltip": "Obs",
  "toggleWindowFocusHotkey": "CmdOrCtrl+Shift+o",
  "quickNoteDateFormat": "YYYY-MM-DD",
  "quickNoteHotkey": ""
}
```

В целом Obsidian полезный, и эта настройка позволяет чаще и проще его тыкать.

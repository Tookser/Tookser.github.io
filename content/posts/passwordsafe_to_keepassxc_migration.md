---
date: 2025-11-12T22:13:08+03:00
title: "Инструкция: как мигрировать БД из PasswordSafe в KeePassXC"
draft: false
author: "Иван"
cover: ""
tags: ["security", "linux", "полезное", "администрирование"]
keywords: ["KeePassXC", "PasswordSafe", "Парольный менеджер"]
description: "Как перенести базу данных из парольного менеджера PasswordSafe -> KeePassXC"
showFullContent: false
readingTime: true
draft: false
---

## Что и зачем

`KeePassXC` - опенсорсный парольный менеджер, он хранит пароли. Он гораздо функциональнее и удобнее, чем `PasswordSafe`.

Чтобы перейти из одного в другой, сохранив пароли - нужна миграция БД из `PasswordSafe` в `KeePassXC`.

Ориентировался на [эту инструкцию](https://infosec.press/ktneely/migrating-passwordsafe-to-keepassxc), но упростил из-за апдейтов программы.


## Подготовка

- Создаём RAM-диск:

```sh
sudo mkdir /mnt/NAME
sudo mount -o size=10M -t tmpfs tmpfs /mnt/NAME
```

(он должен исчезнуть после перезагрузки).

- Устанавливаем [KeePass2x](https://keepass.info/help/v2/setup.html). (он понадобится для промежуточного этапа переноса).
- Устанавливаем [KeePassXC](https://keepassxc.org/).

## **Шаги:**

1. Экспортируем из PasswordSafe в формате .xml _RAM-диск_. (в примере `/mnt/NAME`) Сохраняем все поля.
2. В KeePass2x, создаём шифрованную БД (не рекомендую использовать тот же пароль, что был в PS), уже на обычном диске. Файл должен получить расширение `.kdbx`. 
3. (Опционально) Рекомендуется удалить sample entries, чтобы не отвлекали (2 демонстрационных `entry`, которые есть в новой базе).
4. В KeePass2x, импортируем с диска в оперативной памяти (формат импорта - PasswordSafe XML).
5. Уже в KeePassXC открываем БД, созданную ранее.
6. Удаляем файлы _RAM-диск_ (`/mnt/NAME`).

(Для проверки можно посмотреть `Database -> Database Reports...` и посмотреть на Number of Entries, оно будет тем же, что и в PasswordSafe.)
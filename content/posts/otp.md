---
date: 2025-06-27T10:57:51+03:00
title: "TOTP"
draft: false
author: "Иван"
cover: ""
tags: ["security", "android"]
keywords: ["2FA", "TOTP", "OTP", "HOTP"]
description: "Что такое TOTP, и какие опенсорсные приложения на Android для этого лучше"
showFullContent: false
readingTime: true
draft: false
---

## Что такое TOTP

TOTP - для двухфакторной авторизации. Вместо кода на мобильный телефон (считается небезопасным).

### Схема работы:

1. У клиента и сервера - есть общий секрет.
2. У клиента и сервера - синхронизированы часы.
3. Когда нужно авторизоваться, сервер вычисляет **HASH(T+SECRET)**. T - это количество интервалов времени (например 30-секундных) с [unix epoch](https://en.wikipedia.org/wiki/Unix_time).
4. Клиент тоже считает **HASH(T+SECRET)**.
5. Клиент и сервер берут определённым общеизвестным способом первые цифры от хэша. 
6. Клиент передаёт серверу токен, сервер делает сравнение.

### Возможные уязвимости/проблемы:
1. Может утечь общий секрет, как со стороны клиента, так и со стороны сервера. С кодами на мобильный телефон _именно этого_ не может произойти, к слову.
2. Можно перехватить одноразовый ключ.
3. Может произойти рассинхрон времени: тогда нельзя будет авторизоваться.

- [wiki](https://en.wikipedia.org/wiki/Time-based_one-time_password)
- [ru-wiki](https://ru.wikipedia.org/wiki/TOTP)

## Опенсорсные приложения для Android для TOTP.

Из лучших, рекомендуют 
- [Aegis](https://getaegis.app) (посмотрел, выглядит нормально, есть какая-то защита).
- [freeOTP+](https://github.com/helloworld1/FreeOTPPlus) (пока не смотрел, форк freeOTP).

ещё смотрел
- [secur](https://gitlab.com/ATechnoHazard/secur) - заброшенный, как плюс разве что простота интерфейса.

- [reddit](https://www.reddit.com/r/privacytoolsIO/comments/do46ic/security_of_totp_apps_on_android/) что-то про Aegis и andOTP

## Зачем

Гитхаб требует начать использовать двухфакторку от отдельных аккаунтов.

## HOTP

to be written...
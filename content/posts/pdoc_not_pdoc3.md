+++
title = "pip3 install pdoc"
date = "2022-09-21T22:58:05+03:00"
author = "Иван"
cover = ""
tags = ["программирование", "документация", "тексты"]
keywords = ["pdoc", "pdoc3", "почему два pdoc"]
description = "pip3 install ~~pdoc3~~ pdoc"
showFullContent = false
readingTime = true
draft = false
+++

Есть система автогенерации документации для python (по докстрингам), [pdoc](https://github.com/mitmproxy/pdoc). У неё есть большое преимущество - простота. Есть поиск, подтягивание исходного кода, документирование переменных, форматирование документации, но в целом запускается очень легко.

Корректный способ её установить это

`pip3 install pdoc`

. Кажется, что ~~pdoc3~~ будет лучше, типа это форк и по звёздам на гитхабе уступает мало... Но, [помимо этических проблем](https://github.com/pdoc3/pdoc/issues/64) (не очень дружественный форк как минимум) есть и техническая - при обычном запуске ~~pdoc3~~ в полученной документации отсутствует поиск, а в **pdoc** он получается. Кроме того, дизайн лучше у **pdoc** (readthedocs тема или что-то вроде).

Так запускается pdoc:

`pdoc -o doc_dir/ package_or_module1 package_or_module2 ...`

после чего в папке `doc_dir` создаётся документация, начать можно с `index.html`. 
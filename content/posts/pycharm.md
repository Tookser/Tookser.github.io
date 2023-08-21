+++
title = "Pycharm"
date = "2023-08-22T00:03:20+03:00"
author = "Иван"
cover = ""
tags = ["pycharm", "python"]
keywords = ["pycharm", "pycharm professional", ".idea", "invalid interpreter"]
description = "Ошибка 'Invalid Python Interpreter selected for the project'"
showFullContent = false
readingTime = true
draft = false
+++


Ошибка `Invalid Python Interpreter selected for the project`.
Понадобилось использовать Pycharm (Professional Edition). 

- Сначала создал проект в одной папке
- потом перенёс в другую. 
- Удалил (в линуксе это требуется) подпапку с виртуальной средой `venv/`, создал заново. 
- Результат - среда разработки "не подхватывается", вылезают сообщения об ошибке с упоминанием старого пути.

Решение - закрыть Pycharm PE и стереть подпапку `.idea/`, создаваемую pycharm-ом. При повторном открытии всё сразу подхватывается. Подозреваю, это не единственная проблема которую можно так решить.
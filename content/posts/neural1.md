+++
title = "Промт-инъекция, видео Карпатого и пара быстрых моделей"
date = "2024-03-10T20:36:38+03:00"
author = "Иван"
cover = ""
tags = ["полезное", "нейросети", "aisafety", "LLM", "ai", "ml"]
keywords = ["нейросети", "prompt injection", "LLM attack", "промт-инъекция"]
description = "Небанальная промт-инъекция и две забавных быстрых нейросети"
showFullContent = false
readingTime = true
draft = false
+++

Начал проходить курс "AI Safety fundamentals", и там есть [видео Андрея Карпатого про LLM](https://www.youtube.com/watch?v=zjkBMFhNj_g). Больше половины инфы оттуда я знал, но:

- идея про то, что языковые модели как класс программ ведут себя аналогично операционным системам (_LLM OS_). Подробности по [ссылке](https://www.youtube.com/watch?v=zjkBMFhNj_g&t=2535s) (видео на английском).
- там очень классное описание возможных атак на LLM (промт-инъекций и не только), со ссылками на статьи. Понятно, что это всё прикрывается достаточно быстро.
	- [Jailbroken: How Does LLM Safety Training Fail?](https://arxiv.org/abs/2307.02483)
		- оттуда, например - про base64 кодирование как метод обхода. LLM умеют читать base64, но не защищены.
	- ещё пара статей про отдельные виды атак [(ссылка с таймкодом на последнюю часть видео про это)](https://www.youtube.com/watch?v=zjkBMFhNj_g&t=2743s), в том числе на мультимодальные модели.
	- [Universal and Transferable Adversarial Attacks on Aligned Language Models](https://arxiv.org/abs/2307.15043) - про универсальный, выглядящий набором мусора промт-суффикс. Это надо смотреть.

 ## Пара (ныне недоступных) быстрых моделей
 
- [Groq (ixbt)](https://www.ixbt.com/news/2024/02/20/nikomu-neizvestnyj-startap-groq-predstavil-vidimo-luchshij-processor-dlja-vyvoda-nejrosetevyh-modelej.html) - ASIC (специализированная микросхема) для быстрого инференса LLM. Потыкать можно [тут,](https://groq.com) (там Llama, Mistral, есть платное АПИ), это впечатляет скоростью. В какой-то момент без прокси перестало быть доступным.
- https://fastsdxl.ai - это быстрая генерация картинок, со скоростью ввода. Скорость достигнута в т.ч. благодаря использованию маленькой модели SD XL Lightning. Сейчас недоступна, **обещают вернуться.**
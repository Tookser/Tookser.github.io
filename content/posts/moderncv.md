+++
title = "ModernCV и мытарства"
date = "2022-04-15T14:51:22+03:00"
author = "Иван"
#authorTwitter = "" #do not include @
cover = ""
tags = ["latex", "администрирование", "texlive"]
keywords = ["moderncv", "резюме"]
description = "Как собрать moderncv просто используя TexLive в Docker."
showFullContent = false
readingTime = true
draft = false
+++
Для справки, **LaTeX** - система вёрстки, обычно для научных статей, **Docker** - система для контейнеризации (нечто вроде виртуальной машины).

Немного предыстории. **[ModernCV](https://github.com/moderncv/moderncv)** - шаблон для LaTeX, позволяющий писать красивенькие резюме в pdf. Требует небольшого знания LaTeX-а. В [документации](https://github.com/moderncv/moderncv/raw/master/manual/moderncv_userguide.pdf) можно посмотреть, как выглядит.

Этот шаблон почему-то упорно не хотел нормально собираться на моей системе, и в итоге нашлось более хорошее решение.

Вот [ссылка на docker-образ](https://github.com/moderncv/debian-texlive-docker/pkgs/container/debian-texlive-docker) образ докера с texlive. В нём это резюме собирается следующим образом (рассказываю вариант под Linux с установленным Docker).

Сначала 

`docker pull ghcr.io/moderncv/debian-texlive-docker:main` - скачивание docker-образа.

Потом создаём контейнер

`docker run -it -v "/путь/к/папке/с/резюме:/mnt" --name ИмяОбраза ghcr.io/moderncv/debian-texlive-docker:main /bin/bash`

Это создаёт docker-контейнер по скачанному docker-образу. _ИмяОбраза_ и _/путь/к/папке/с/резюме_ (на вашем диске) нужно заполнить самим. `-it` позволяет работать в терминале внутри контейнера, `-v` монтирует папку к пути `/mnt` внутри докер-контейнера (да, прямо в него, но это не столь важно).

Остаётся только запускать контейнер с помощью этой команды.

`docker exec -it ИмяОбраза /bin/bash`

, вы окажетесь в терминале, откуда уже можно собрать резюме с помощью TexLive, зайдя в директорию `/mount` (внутри контейнера; с вашей ничего не случится). Возможно, понадобится что-то догрузить из пакетов - `sudo apt install ...` вполне помогало, если вообще понадобилось.
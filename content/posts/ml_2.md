+++
title = "MCP - протокол для взаимодействия LLM с сервисами"
date = "2025-03-26T21:35:11+03:00"
author = "Иван"
cover = ""
tags = ["ai", "ml", "agency"]
keywords = ["нейронные сети", "LLM", "агентные модели", "MCP"]
description = "USB-C для нейросетей"
showFullContent = false
readingTime = true
draft = false
+++


За два дня дважды в разных местах попалось упоминание MCP (Model Context Protocol) (открытая технология Anthropic). 

Что это:

- [https://modelcontextprotocol.io/introduction](https://modelcontextprotocol.io/introduction) ссылка на введение в протокол. Может смущать наличие и host, и client, и server: как я понял почитав сайт, основная единица это server, который отвечает на запросы, которые client делает (по указке hostа). 
- [https://mcp.so/](https://mcp.so/) тут много примеров MCP.
- [https://habr.com/ru/articles/893482/](https://habr.com/ru/articles/893482/) - статья про MCP (краткая обзорная часть и примеры кода).

См. также [LSP](https://en.wikipedia.org/wiki/Language_Server_Protocol) :-) (который во многом похожее делает).

(С точки зрения AI Safety... пф-пф-пф. Ну, клиент может обрубать некорректные запросы от хоста. Можно сделать сервер-gateway, который будет ограничивать права в зависимости от).
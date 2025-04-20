[JS библиотека](/api_help/js_lib/index.php)

[AJAX расширение](/api_help/js_lib/ajax/index.php)

BX.ajax.loadJSON

BX.ajax.loadJSON
================

```
XMLHttpRequest
BX.ajax.loadJSON(
	string url,
	function callback[,
	function callback_failure]
);Копировать
```

или:

```
XMLHttpRequest
BX.ajax.loadJSON(
	string url,
	object data,
	function callback[,
	function callback_failure]
);Копировать
```

Функция загружает json-объект из заданного **url** и передает его обработчику **callback**.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| url | Адрес |
| data | GET-данные запроса |
| callback | Обработчик |
| callback\_failure | обработчик ошибочной ситуации |

Новинки документации в соцсетях:
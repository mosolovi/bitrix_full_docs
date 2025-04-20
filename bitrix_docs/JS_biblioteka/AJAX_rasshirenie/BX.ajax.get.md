[JS библиотека](/api_help/js_lib/index.php)

[AJAX расширение](/api_help/js_lib/ajax/index.php)

BX.ajax.get

BX.ajax.get
===========

Функция допускает два варианта входных параметров.

```
XMLHttpRequest 
BX.ajax.get(
	string url,
	string|object data,
	function callback
);Копировать
```

```
XMLHttpRequest 
BX.ajax.get(
	string url,
	function callback
);Копировать
```

Отправка GET-запроса и передача результата обработчику **callback**.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| url | Адрес |
| data | Строка или ассоциативный массив GET-параметров запроса (которые можно просто указать в адресе) |
| callback | Обработчик |

Новинки документации в соцсетях:
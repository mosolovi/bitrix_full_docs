[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Утилиты](/api_help/js_lib/kernel/utilits/index.php)

BX.parseJSON

BX.parseJSON
============

```
BX.parseJSON(
	string data,
	context
);Копировать
```

Возвращает переданную строку как JSON-объект.

**Примечание**: В случае ошибки парсинга строки будет вызвано событие **onParseJSONFailure**.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| string data | Строка |
| context | Необязательный. В случае ошибки (и вызова onParseJSONFailure) вторым параметром обработчику будет передан данный контекст. |

#### Примеры использования

```
BX.parseJSON('{test: 123}');
Object {test: 123} Копировать
```

Новинки документации в соцсетях:
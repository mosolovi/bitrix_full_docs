[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Утилиты](/api_help/js_lib/kernel/utilits/index.php)

BX.processHTML

BX.processHTML
==============

```
object 
BX.processHTML(
	string HTML
);Копировать
```

Разбор строки HTML с вставками js. Результат будет представлять собой объект:

```
{
	HTML: очищенный HTML,
	SCRIPT: [
		{
			JS: строка скрипта или имя внешнего файла,
			isInternal: true|false – является ли запись готовым скриптом или внешним файлом
		}
	],
	STYLE: [
		массив подключаемых в коде внешних стилей.
	]
}Копировать
```

Необходим для работы аяксового расширения.

Новинки документации в соцсетях:
[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Утилиты](/api_help/js_lib/kernel/utilits/index.php)

BX.loadScript

BX.loadScript
=============

Загрузить и выполнить скрипт или серию скриптов. Скрипты будут загружены средствами DOM, без XMLHttpRequest.

```
void 
BX.loadScript(
	string|array script[,
	function callback[
	DOMDocument doc]]
);Копировать
```

Функция загрузит и выполнит скрипт или серию скриптов. Скрипты будут загружены средствами **DOM**, без **XMLHttpRequest**. Если передан массив скриптов и обработчик, то обработчик будет вызван после загрузки всех скриптов

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| script | Исполняемый скрипт |
| *callback* | Обработчик |
| *DOMDocument doc* |  |

Новинки документации в соцсетях:
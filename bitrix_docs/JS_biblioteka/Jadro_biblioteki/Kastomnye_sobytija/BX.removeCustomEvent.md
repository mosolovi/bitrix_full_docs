[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Кастомные события](/api_help/js_lib/kernel/castom_events/index.php)

BX.removeCustomEvent

BX.removeCustomEvent
====================

Функция допускает два варианта входных параметров.

```
void 
BX.removeCustomEvent(
	Object eventObject,
	string eventName, 
	Function eventHandler
);Копировать
```

```
void 
BX.removeCustomEvent(
	string eventName, 
	Function eventHandler
);Копировать
```

Функция удаляет обработчик **eventHandler** кастомного события с именем **eventName**.

Новинки документации в соцсетях:
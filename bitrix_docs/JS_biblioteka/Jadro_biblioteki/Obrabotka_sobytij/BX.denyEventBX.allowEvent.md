[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Обработка событий](/api_help/js_lib/kernel/events/index.php)

BX.denyEvent/BX.allowEvent

BX.denyEvent/BX.allowEvent
==========================

```
void 
BX.denyEvent(
	DOMNode element,
	string event
);Копировать
```

```
void 
BX.allowEvent(
	DOMNode element,
	string event
);Копировать
```

Два метода, позволяющих временно отключить и включить обработку конкретного события в конкретном элементе. Пока что отключаются только обработчики, назначенные через `element['on' + event]`.

Новинки документации в соцсетях:
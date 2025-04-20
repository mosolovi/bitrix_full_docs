[JS библиотека](/api_help/js_lib/index.php)

[Работа с локальным хранилищем](/api_help/js_lib/ls/index.php)

BX.onGlobalCustomEvent

BX.onGlobalCustomEvent
======================

```
void
BX.onGlobalCustomEvent(
	String eventName,
	Array arEventParams[,
	Boolean bSkipSelf = false]
);Копировать
```

Функция выполняет обработчики кастомного события eventName ([BX.addCustomEvent](/api_help/js_lib/kernel/castom_events/bx_addcustomevent.php)/[BX.onCustomEvent](/api_help/js_lib/kernel/castom_events/bx_oncustomevent.php)) во всех вкладках браузера

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| eventName | Название события |
| arEventParams | Массив параметров события |
| bSkipSelf | Позволяет пропустить обработчики текущей вкладки, в которой был вызов. По умолчанию *false* |

Новинки документации в соцсетях:
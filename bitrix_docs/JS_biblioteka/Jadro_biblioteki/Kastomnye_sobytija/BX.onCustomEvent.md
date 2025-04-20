[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Кастомные события](/api_help/js_lib/kernel/castom_events/index.php)

BX.onCustomEvent

BX.onCustomEvent
================

Функция позволяет два варианта входных параметров.

```
void 
BX.onCustomEvent(
	Object eventObject,
	string eventName[,
	Array arEventParams]
);Копировать
```

```
void 
BX.onCustomEvent(
	string eventName[,
	Array arEventParams]
);Копировать
```

Функция вызывает все обработчики события **eventName** для объекта **eventObject**, а также, все глобальные обработчики (назначенные без указания объекта). Если не указан объект, в котором возникает событие, то будут вызваны только глобальные обработчики. Обработчик будет выполнен в контексте объекта, в котором возникло событие. Значения из массива **arEventParams** будут переданы в качестве входных параметров обработчика..

Новинки документации в соцсетях:
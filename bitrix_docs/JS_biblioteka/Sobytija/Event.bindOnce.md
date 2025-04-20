[JS библиотека](/api_help/js_lib/index.php)

[События](/api_help/js_lib/events/index.php)

Event.bindOnce

Event.bindOnce
==============

```
Event.bindOnce(target: Element, event: string, handler: (event: Event) => void, options?: listenerOptions)Копировать
```

Добавляет обработчик указанного события, который будет вызван только один раз.

```
import {Event} from 'main.core';
const button = document.querySelector('.ui-btn');
Event.bindOnce(button, 'click', (event) => {
	// ...
});Копировать
```

Новинки документации в соцсетях:
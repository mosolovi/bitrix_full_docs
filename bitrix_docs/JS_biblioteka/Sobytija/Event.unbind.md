[JS библиотека](/api_help/js_lib/index.php)

[События](/api_help/js_lib/events/index.php)

Event.unbind

Event.unbind
============

```
Event.unbind(target: Element, event: string, handler: (event: Event) => void, options?: listenerOptions)Копировать
```

Удаляет указанный обработчик события. В качестве третьего параметра необходимо передать параметры, с которыми был добавлен обработчик. Если обработчик был добавлен без параметров, то параметры передавать не нужно.

```
import {Event} from 'main.core';
const button = document.querySelector('.ui-btn');
Event.unbind(button, 'click', eventHandler);Копировать
```

Новинки документации в соцсетях:
[JS библиотека](/api_help/js_lib/index.php)

[События](/api_help/js_lib/events/index.php)

Event.unbindAll

Event.unbindAll
===============

```
Event.unbindAll(target: any, event?: string)Копировать
```

Удаляет все обработчики указанного события.

```
import {Event} from 'main.core';
const button = document.querySelector('.ui-btn');
Event.unbindAll(button, 'click');Копировать
```

Новинки документации в соцсетях:
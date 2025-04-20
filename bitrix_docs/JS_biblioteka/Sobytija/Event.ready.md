[JS библиотека](/api_help/js_lib/index.php)

[События](/api_help/js_lib/events/index.php)

Event.ready

Event.ready
===========

```
Event.ready(() => void)Копировать
```

Добавляет обработчик, который будет выполнен после загрузки страницы. Если страница уже была загружена, то обработчик будет выполнен немедленно.

```
import {Event} from 'main.core';
Event.ready(() => {
	console.log('Page loaded!');
});Копировать
```

Новинки документации в соцсетях:
[JS библиотека](/api_help/js_lib/index.php)

[События](/api_help/js_lib/events/index.php)

Event.BaseEvent

Event.BaseEvent
===============

Класс-конструктор объекта события.

```
import {Event} from 'main.core';
const event = new Event.BaseEvent({
	data: {
		item1: '...',
		item2: '...',
	},
});
this.emit('BX.UI.Button:click', event);Копировать
```

  

#### Event.BaseEvent.preventDefault

```
Event.BaseEvent.preventDefault()Копировать
```

Отменяет действие по умолчанию для события.

  

#### Event.BaseEvent.isDefaultPrevented

```
Event.BaseEvent.isDefaultPrevented(): booleanКопировать
```

Проверяет была ли отмена действия по умолчанию в обработчике события.

  

#### Event.BaseEvent.isTrusted

```
Event.BaseEvent.isTrusted: booleanКопировать
```

Указывает на то, кем было отправлено событие.

Если *true*, то событие было отправлено объектом наследником класса [Event.EventEmitter](/api_help/js_lib/events/eventemitter.php).  
Если *false*, то событие было отправлено глобально, с помощью статического метода **.emit**

Новинки документации в соцсетях:
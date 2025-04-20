[JS библиотека](/api_help/js_lib/index.php)

[События](/api_help/js_lib/events/index.php)

Event.bind

Event.bind
==========

```
Event.bind(target: Element, event: string, handler: (event: Event) => void, options?: listenerOptions)Копировать
```

Добавляет обработчик указанного события, который будет вызваться всякий раз при возникновении события. В качестве третьего параметра функция может принимать объект определяющий свойства обработчика события.

```
const listenerOptions = {
	capture?: boolean,
	once?: boolean,
	passive?: boolean,
}
import {Event} from 'main.core';
const button = document.querySelector('.ui-btn');
Event.bind(button, 'click', (event) => {
	// ...
});Копировать
```

**Добавление неблокирующего обработчика.**

```
import {Event} from 'main.core';
Event.bind(window, 'scroll', scrollHandler, {passive: true});Копировать
```

Такой обработчик не будет блокировать выполнение действия по умолчанию. В данном случае перерисовка страницы при прокрутке будет происходить сразу, не дожидаясь выполнения обработчика. Все вызовы event.preventDefault() в таком обработчике игнорируются.

Новинки документации в соцсетях:
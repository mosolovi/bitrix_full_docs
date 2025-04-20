[JS библиотека](/api_help/js_lib/index.php)

[События](/api_help/js_lib/events/index.php)

Event.EventEmitter

Event.EventEmitter
==================

Включить вкладки

Описание

Event.EventEmitter.subscribe

Event.EventEmitter.subscribeOnce

Event.EventEmitter.unsubscribe

Event.EventEmitter.emit

Event.EventEmitter.emitAsync

Event.EventEmitter.setMaxListeners

Event.EventEmitter.getMaxListeners

Event.EventEmitter.getListeners

### Описание

Класс реализует интерфейс EventEmitter'а для работы с кастомными событиями.

```
import {Event} from 'main.core';
// Отправка событий в классе наследнике 
class Button extends Event.EventEmitter
{
	constructor()
	{
		super();
		// Отправка события BX.MyModule.MyClass:ready
		this.emit('BX.UI.Button:ready');
	}
	
	render()
	{
		// Отправка события BX.MyModule.MyClass:beforeRender
		this.emit('BX.UI.Button:beforeRender');
		// ... 
		// Отправка события BX.MyModule.MyClass:render
		this.emit('BX.UI.Button:render');
	}
	
	onClick()
	{
		const event = new Event.BaseEvent({data: {...}});
		// Отправка события BX.MyModule.MyClass:render
		this.emit('BX.UI.Button:click', event);
	}
}Копировать
```

**Подписка на события объекта**

```
const button = new Button();
button
	.subscribe('BX.UI.Button:ready', (event) => {
		console.log('Button is ready', event);
	})
	.subscribe('BX.UI.Button:render', (event) => {
		console.log('Button is rendered', event);
	})
	.subscribe('BX.UI.Button:click', (event) => {
		console.log('Button is clicked', event);
	});Копировать
```

**Глобальная подписка на события всех объектов**

```
Event.EventEmitter
	.subscribe('BX.UI.Button:ready', (event) => {
		console.log('Button is ready', event);
	})
	.subscribe('BX.UI.Button:render', (event) => {
		console.log('Button is rendered', event);
	})
	.subscribe('BX.UI.Button:click', (event) => {
		console.log('Button is clicked', event);
	});
Копировать
```

**Глобальная отправка событий**

```
Event.EventEmitter
	.emit('BX.UI.Button:click');Копировать
```

Будут вызваны все обработчики события **BX.UI.Button:click**.

### Event.EventEmitter.subscribe

```
Event.EventEmitter.subscribe(event: any, listener: (event: BaseEvent) => void): EventEmitterКопировать
```

Добавляет обработчик указанного события. В качестве первого параметра в обработчик передается объект типа BaseEvent.

```
import {Event} from 'main.core';
class Button extends Event.EventEmitter {}
const emitter = new Button();
emitter.subscribe('BX.UI.Button:click', (event) => {
	// ...
});Копировать
```

### Event.EventEmitter.subscribeOnce

```
Event.EventEmitter.subscribeOnce(event: any, listener: (event: BaseEvent) => void): EventEmitterКопировать
```

Добавляет обработчик указанного события, который будет вызван только один раз.

```
import {Event} from 'main.core';
class Button extends Event.EventEmitter {}
const emitter = new Button();
emitter.subscribeOnce('BX.UI.Button:click', (event) => {
	// ...
});Копировать
```

### Event.EventEmitter.unsubscribe

```
Event.EventEmitter.unsubscribe(event: any, listener: Function) => void): EventEmitterКопировать
```

Удаляет обработчик события.

```
import {Event} from 'main.core';
class Button extends Event.EventEmitter {}
const emitter = new Button();
emitter.subscribeOnce('BX.UI.Button:click', clickHandler);Копировать
```

### Event.EventEmitter.emit

```
Event.EventEmitter.emit(eventName: any, event?: BaseEvent | {[key: string]: any}): EventEmitterКопировать
```

Отправляет событие.

```
import {Event} from 'main.core';
// Отправка событий в классе наследнике 
class Button extends Event.EventEmitter
{
	constructor()
	{
		super();
		// Отправка события BX.MyModule.MyClass:ready
		this.emit('BX.UI.Button:ready');
	}
	
	// ...
}Копировать
```

### Event.EventEmitter.emitAsync

```
Event.EventEmitter.emitAsync(eventName: any, event?: BaseEvent | {[key: string]: any}): PromiseКопировать
```

Отправляет событие и возвращает Promise, который будет решен, когда решатся все промисы возвращенные из обработчиков события или отклонен, когда хотя бы один из возвращенных промисов будет отклонен.

Обратите внимание, что промис решается со значением типа Array, содержащим значения промисов вернувшихся из обработчиков. Порядок значений соответствует порядку подписки обработчиков, а не порядку решения промисов.

Также, обратите внимание на то, что из синхронных обработчиков не обязательно возвразать промис, можно просто вернуть значение любого типа. Либо вообще ничего не возвращать.

```
import {Event} from 'main.core';
class Button extends Event.EventEmitter {}
const button = new Button();
button.subscribe('click', () => {
	return new Promise((resolve) => {
		setTimeout(() => {
			resolve('value 1');
		}, 1000);  
	});
});
button.subscribe('click', () => {
	return 'value 2';
});
button
	.emitAsync('click')
	.then((results) => {
		console.log(result[0]); // => 'value 1'
		console.log(result[1]); // => 'value 2'
	});Копировать
```

### Event.EventEmitter.setMaxListeners

```
Event.EventEmitter.setMaxListeners(count: number): EventEmitterКопировать
```

Устанавливает максимальное количество обработчиков для каждого события. По умолчанию 10. Если количество обработчиков превысит максимальное количество, то в консоль будет выведено предупреждение.

```
import {Event} from 'main.core';
class Button extends Event.EventEmitter {}
const emitter = new Button();
emitter.setMaxListeners(2);
emitter
	.subscribe('BX.UI.Button:click', () => {})
	.subscribe('BX.UI.Button:click', () => {})
	.subscribe('BX.UI.Button:click', () => {});
// => Possible BX.Event.EventEmitter memory leak detected. 3 BX.UI.Button:click listeners added. Use emitter.setMaxListeners() to increase limitКопировать
```

### Event.EventEmitter.getMaxListeners

```
Event.EventEmitter.getMaxListeners(): NumberКопировать
```

Возвращает текущий лимит на количество обработчиков для каждого события.

### Event.EventEmitter.getListeners

```
Event.EventEmitter.getListeners(eventName: any): Set | nullКопировать
```

Возвращает список обработчиков указанного события.

Новинки документации в соцсетях:
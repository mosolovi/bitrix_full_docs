[JS библиотека](/api_help/js_lib/index.php)

[Runtime](/api_help/js_lib/runtime/index.php)

Runtime.loadExtension

Runtime.loadExtension
=====================

```
Runtime.loadExtension(name: string|Array): Promise<{[key: string]: any} | Function | null>Копировать
```

Позволяет выполнить отложенное подключение [экстеншна](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=11981) на страницу. Может оказаться полезным, когда функционал показывается на странице не сразу, а, например, в открывшемся pop-up, табе и т. п.

Функция **Runtime.loadExtension** возвращает промис, в значение которого передаются все экспорты подключаемого экстеншна.

Например, если подключить расширение `main.loader`, то в значении промиса будет ссылка на объект `{Loader: Function}`.

```
import {Runtime} from 'main.core';
Runtime.loadExtension('main.loader').then((exports) => {
	console.log(exports); // {Loader: Function}
	
	const {Loader} = exports;
	const loader = new Loader();
	
	loader.show();
});Копировать
```

Если экстеншн уже подключен на страницу, то функция **Runtime.loadExtension** вернет сразу решенный промис с ссылкой на объект экспортов (т. е. повторное подключение не произойдёт).

Новинки документации в соцсетях:
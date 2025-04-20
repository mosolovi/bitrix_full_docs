[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Управление DOM-структурой](/api_help/js_lib/kernel/dom_control/index.php)

BX.toggleClass

BX.toggleClass
==============

```
DOMNode 
BX.toggleClass(
	DOMNode node, 
	string|array className
);Копировать
```

Функция переключает наличие/отсутствие CSS-класса **className** у узла **node** или производит ротацию CSS-классов, если **className** – массив.

#### Примеры

```
BX.ready(function(){
	BX.bind(BX("test"), "click", function() {
		BX.toggleClass(BX("test"), ["arrowUp", "arrowDown"]);
	});
})Копировать
```

Новинки документации в соцсетях:
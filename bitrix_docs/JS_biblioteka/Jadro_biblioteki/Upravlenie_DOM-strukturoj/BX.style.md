[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Управление DOM-структурой](/api_help/js_lib/kernel/dom_control/index.php)

BX.style

BX.style
========

```
string|DOMNode 
BX.style(
	DOMNode node,
	string property[,
	string value]
);Копировать
```

Функция позволяет получить текущее значение стиля **property** узла **node** или установить его в значение **value**. Свойство **property** указывается в CSS-нотации (например, **'margin-right'**)

#### Пример

```
BX.style(document.body, 'padding', '200px 100px');
alert(BX.style(document.body, 'padding-top')); //200pxКопировать
```

Новинки документации в соцсетях:
[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Обработка событий](/api_help/js_lib/kernel/events/index.php)

BX.bind

BX.bind
=======

```
void 
BX.bind(
	Object|DOMNode el, 
	String event,
	Function handler
);Копировать
```

Функция устанавливает функцию **handler** в качестве обработчика события **event** элемента **el**.

#### Примечание

Использование BX.delegate (или BX.proxy) предпочтительнее. Это позволит:

1. делать BX.unbind
2. не плодить код, а вешать один и тот же обработчик на несколько элементов.

#### Примеры использования

```
BX.bind(BX('test'), 'click', function() {alert('click!')})Копировать
```

Получить непосредственно элемент, по которому кликнули.

```
_hadleMoreButtonClickHandler: function(e)
{
	alert(BX.proxy_context.innerHTML);
}
BX.bind(BX('test'), 'click', BX.delegate(this._hadleMoreButtonClickHandler, this));Копировать
```

Новинки документации в соцсетях:
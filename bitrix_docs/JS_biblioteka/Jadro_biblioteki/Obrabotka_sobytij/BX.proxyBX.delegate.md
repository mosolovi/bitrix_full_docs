[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Обработка событий](/api_help/js_lib/kernel/events/index.php)

BX.proxy/BX.delegate

BX.proxy/BX.delegate
====================

Включить вкладки

Описание

Примеры использования

### Описание

```
Function 
BX.proxy(
	Function func,
	Object context
);Копировать
```

```
Function 
BX.delegate(
	Function func,
	Object context
);Копировать
```

Две родственных функции, генерирующих «функцию-делегата», которая будет вызывать требуемую функцию в нужном контексте. Это может использоваться, например, для назначения метода какого-либо объекта в качестве обработчика события с сохранением контекста объекта.

Отличие между функциями в том, что **BX.proxy** при повторном вызове с теми же параметрами вернет не новую функцию-делегата, а ссылку на сгенерированную до этого функцию, что может быть полезно, например, если требуется отменить конкретный обработчик события.

**Примечание**: BX.delegate - аналог [jQuery.proxy](http://api.jquery.com/jQuery.proxy/).

### Примеры использования

Код для получения элемента, по которому был произведен клик:

```
_hadleMoreButtonClickHandler: function(e)
{
	alert(BX.proxy_context.innerHTML);
}
BX.bind(BX('test'), 'click', BX.delegate(this._hadleMoreButtonClickHandler, this));Копировать
```

```
<script type="text/javascript">
function MyClass()
{
	this.prop = 1;
	BX.bind(BX('link'), 'click', BX.proxy(this.handler, this));
}
MyClass.prototype.handler = function()
{
	alert(this.prop);
	BX.unbind(BX('link'), 'click', BX.proxy(this.handler, this));
}
BX.ready(function(){ new MyClass(); });
</script>
<a href="javascript:void(0)" id="link">Click Me</a>Копировать
```

```
function MyClass(){}
MyClass.prototype.handler = function(){}
var ob = new MyClass();
alert(BX.delegate(ob.handler, ob) == BX.delegate(ob.handler, ob)); // false
alert(BX.proxy(ob.handler, ob) == BX.proxy(ob.handler, ob)); // trueКопировать
```

Также приведем более практический пример, демонстрирующий передачу контекста исполнения при делегировании. Представим, что вызывается анонимная функция в следующем контексте:

```
My.prototype.test = function(d)
{
	console.log(d);
};
My.prototype.send = function()
{
	BX.ajax.get(this._ajaxPage, post, function(data){
		this.test(data);
	});
};Копировать
```

Достаточно стандартная ситуация, когда после ajax-запроса мы совершаем какие-то действия с данными. Однако при исполнении приведенного кода строка **this.test(data);** приведет к ошибке (т.к. в данном контексте **this** будет ссылаться на саму анонимную функцию). Для сохранения прозрачности кода достаточно обернуть вызов анонимной функции в **BX.delegate**:

```
My.prototype.test = function(d)
{
	console.log(d);
};
My.prototype.send = function()
{
	BX.ajax.get(this._ajaxPage, post, BX.delegate(function(data){
		this.test(data);
	}, this));
};Копировать
```

На этот раз строка **this.test(data)** выполнится без ошибок и обратится к методу вашего класса **My**.

Новинки документации в соцсетях:
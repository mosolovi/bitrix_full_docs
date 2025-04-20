[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Обработка событий](/api_help/js_lib/kernel/events/index.php)

BX.bindDelegate

BX.bindDelegate
===============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
Function
BX.bindDelegate(
	DOMNode node,
	String eventName,
	Object isTarget,
	Function handler
);Копировать
```

Функция устанавливает обработчик **handler** события **eventName** на дочерние элементы узла **node**, удовлетворяющих условиям **isTarget**. Нюансом метода является независимость от изменений содержимого node: физически обработчик вешается на сам узел node и принимает событие в момент его всплывания от дочерних элементов.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| node | Родительский узел |
| eventName | Имя события |
| isTarget | Описание дочерних узлов в формате, аналогичном используемому в функциях поиска |
| handler | Обработчик события |

#### Возвращаемое значение

Ссылка на реально устанавливаемый обработчик события, которую можно использовать, например, для [BX.unbind](/api_help/js_lib/kernel/events/bx_unbind.php).

### Примеры использования

```
<style>#my_node td {padding: 2px; height: 30px; width: 30px; text-align: center;}</style>
<table id="my_node" cellpadding="2" cellspacing="0" border="1">
	<tr><td></td><td></td><td></td></tr>
	<tr><td></td><td></td><td></td></tr>
	<tr><td></td><td></td><td></td></tr>
</table>
<script>
var sign = 'x';
BX.bindDelegate(
	BX('my_node'),
	'click',
	{
		tagName: 'TD'
	},
	function()
	{
		this.innerHTML = sign;
		sign = sign == 'x' ? 'o' : 'x';
	}
);
</script>Копировать
```

Новинки документации в соцсетях:
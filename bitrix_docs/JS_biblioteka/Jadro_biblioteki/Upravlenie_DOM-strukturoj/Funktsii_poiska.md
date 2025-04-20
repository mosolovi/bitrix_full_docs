[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Управление DOM-структурой](/api_help/js_lib/kernel/dom_control/index.php)

Функции поиска

Функции поиска
==============

Включить вкладки

Описание

Параметры функции

Примеры использования

Функционал устарел. Используйте стандартные методы **.querySelectorAll** и **.querySelector**.

### Описание

```
Array|DOMNode 
BX.findChild(
	DOMNode obj,
	Object params, 
	bool recursive
	get_all
);Копировать
```

```
array|DOMNode 
BX.findChildren(
	DOMNode obj,
	Object params, 
	bool recursive
);Копировать
```

```
DOMNode 
BX.findParent(
	DOMNode obj,
	Object params, 
);Копировать
```

```
DOMNode 
BX.findNextSibling(
	DOMNode obj,
	Object params, 
);Копировать
```

```
DOMNode 
BX.findPreviousSibling(
	DOMNode obj,
	Object params, 
);Копировать
```

Функции поиска узлов DOM-структуры по набору параметров.

**Примечание**: `BX.findChildren(obj, params, recursive)` - синоним `BX.findChild(obj, params, recursive, true)`.

### Параметры функции

| Параметр | Описание |
| --- | --- |
| DOMNode obj | Объект поиска |
| params | Формат объекта, описывающего параметры поиска:  * **tagName|tag**: имя тэга требуемого узла, * **className|class**: CSS-класс, который должен содержать требуемый узел, * **attribute**: {attribute: value, attribute: value} | attribute | [attribute, attribute....], - либо объект со списком и конкретными значениями атрибутов, либо атрибут или массив атрибутов, которые должны присутствовать в требуемом узле * **property**: {prop: value, prop: value} | prop | [prop, prop] - либо объект со свойств и конкретными значениями свойств, либо свойство или массив свойств, которые должны присутствовать в требуемом узле   **Примечание:** Вместо набора параметров можно указать фильтрующую функцию, которая будет вызываться для каждого проверяемого узла DOM-структуры. Функция должна вернуть true или false. |
| recursive | показывает, что нужно искать не только непосредственно в дочерних элементах узла, а во всем поддереве. По умолчанию – *false* (только в дочерних). |
| get\_all | вернуть все найденные элементы в виде массива. |

### Примеры использования

```
var body = BX.findParent(BX("bx-panel"), {"tag" : "body"});
console.log(body);Копировать
```

```
obSelect = BX.findChild(BX("menu"), {
	"tag" : "li",
	"class" : "select"
}, 
true
);Копировать
```

```
obNotEmptyListItem = BX.findChild(
	BX("menu"), 
	function(el) {
		return el.tagName.toUpperCase() == 'LI' && !!el.firstChild
	}, 
	true
);Копировать
```

Пример-аналог `$.each:` находим всех пасынков id `BX(this._id + '_placeholder')` с классом **crm-qpe-field**, применяем к ним некие действия.

```
var fields = BX.findChild(BX(this._id + '_placeholder'), {class: 'crm-qpe-field'}, true, true);
fields.forEach(function(element){
	console.log(element.getAttribute('name'));
});Копировать
```

На jquery это примерно так:

```
$.each($( '#' + this ._id + '_placeholder .crm-qpe-field'), function(i, e){
	console.log($(e).attr('name'));
});Копировать
```

Новинки документации в соцсетях:
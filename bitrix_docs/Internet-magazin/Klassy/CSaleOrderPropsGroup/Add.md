[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderPropsGroup](/api_help/sale/classes/csaleorderpropsgroup/index.php)

Add (доступен с 3.3.5)

Add
===

```
int
CSaleOrderPropsGroup::Add(
	array arFields
);Копировать
```

Метод добавляет новую группу свойств заказа. Группа используется только для группировки свойств. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arFields | Ассоциативный массив параметров группы свойств, в котором ключами являются названия параметров, а значениями - их значения.  Допустимые ключи:  * **PERSON\_TYPE\_ID** - тип плательщика; * **NAME** - название группы (группа привязывается к типу плательщика, тип плательщика привязывается к сайту, сайт привязывается к языку, название задается на этом языке); * **SORT** - индекс сортировки. |

#### Возвращаемые значения

Возвращается код добавленной группы или *false* в случае ошибки.

Новинки документации в соцсетях:
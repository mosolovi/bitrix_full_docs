[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderPropsGroup](/api_help/sale/classes/csaleorderpropsgroup/index.php)

Update (доступен с 3.3.0)

Update
======

```
int
CSaleOrderPropsGroup::Update(
	int ID,
	array arFields
);Копировать
```

Метод обновляет параметры группы заказов с кодом ID на параметры из массива arFields. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код группы заказов. |
| arFields | Ассоциативный массив параметров группы свойств, в котором ключами являются названия параметров, а значениями - новые значения.   Допустимые ключи:  * **PERSON\_TYPE\_ID** - тип плательщика; * **NAME** - название группы (группа привязывается к типу плательщика, тип плательщика привязывается к сайту, сайт привязывается к языку, название задается на этом языке); * **SORT** - индекс сортировки. |

#### Возвращаемые значения

Возвращается код добавленной группы или *false* в случае ошибки.

Новинки документации в соцсетях:
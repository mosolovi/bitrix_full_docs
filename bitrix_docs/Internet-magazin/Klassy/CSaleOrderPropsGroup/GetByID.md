[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderPropsGroup](/api_help/sale/classes/csaleorderpropsgroup/index.php)

GetByID (доступен с 3.3.0)

GetByID
=======

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
array
CSaleOrderPropsGroup::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры группы свойств заказа с кодом ID. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код группы заказов. |

#### Возвращаемые значения

Возвращается ассоциативный массив параметров группы свойств с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код группы заказов. |
| PERSON\_TYPE\_ID | Тип плательщика. |
| NAME | Название группы. |
| SORT | Индекс сортировки. |

### Пример использования

```
<?
if ($arPropsGroup = CSaleOrderPropsGroup::GetByID(3))
	echo $arPropsGroup["NAME"];
?>Копировать
```

Новинки документации в соцсетях:
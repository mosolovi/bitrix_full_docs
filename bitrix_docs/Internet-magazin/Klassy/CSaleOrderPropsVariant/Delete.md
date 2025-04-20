[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderPropsVariant](/api_help/sale/classes/csaleorderpropsvariant/index.php)

Delete (доступен с 3.3.0)

Delete
======

```
bool
CSaleOrderPropsVariant::Delete(
	int ID
);Копировать
```

Метод удаляет вариант с кодом ID значения свойства заказа. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код варианта значения свойства заказа. |

#### Возвращаемые значения

Возвращается *true* в случае успешного удаления и *false* - в случае ошибки.

#### Пример использования

```
<?
CSaleOrderPropsVariant::Delete(12);
?>Копировать
```

Новинки документации в соцсетях:
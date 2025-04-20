[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderUserPropsValue](/api_help/sale/classes/csaleorderuserpropsvalue/index.php)

Delete (доступен с 3.3.0)

Delete
======

```
bool
CSaleOrderUserPropsValue::Delete(
	int ID
);Копировать
```

Метод удаляет свойство с кодом ID профиля покупателя. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код свойства профиля покупателя. |

#### Возвращаемые значения

Возвращается *true* в случае успешного удаления и *false* - в противном случае.

#### Пример использования

```
<?
CSaleOrderUserPropsValue::Delete(17);
?>Копировать
```

Новинки документации в соцсетях:
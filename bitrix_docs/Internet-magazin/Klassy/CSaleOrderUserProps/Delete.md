[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderUserProps](/api_help/sale/classes/csaleorderuserprops/index.php)

Delete (доступен с 3.3.0)

Delete
======

```
bool
CSaleOrderUserProps::Delete(
	int ID
);Копировать
```

Метод удаляет профиль покупателя с кодом ID. Вместе с профилем удаляются все его свойства. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код профиля покупателя. |

#### Возвращаемые значения

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php) в случае успешного удаления и *false* - в противном случае.

Новинки документации в соцсетях:
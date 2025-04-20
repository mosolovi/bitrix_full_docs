[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderUserPropsValue](/api_help/sale/classes/csaleorderuserpropsvalue/index.php)

Update (доступен с 11.0.0)

Update
======

```
array
CSaleOrderUserPropsValue::Update(
	$ID,
	$arFields
);Копировать
```

Метод обновляет свойство профиля покупателя в соответствии с массивом параметров arFields. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор свойства профиля покупателя. Его можно узнать посмотрев все свойства определённого профиля методом [CSaleOrderUserPropsValue::GetList](/api_help/sale/classes/csaleorderuserpropsvalue/csaleorderuserpropsvalue__getlist.19b444a8.php). |
| arFields | Массив значений свойств. |

| Ключ | Описание |
| --- | --- |
| ID | Идентификатор свойства профиля покупателя. Несмотря на то, что этот идентификатор передаётся как параметр, его необходимо обязательно продублировать в качестве ключа массива **arFields**. В противном случае будет ошибка. Идентификатор сожно узнать, например, посмотрев все профили пользователя методом [CSaleOrderUserProps::GetList](/api_help/sale/classes/csaleorderuserprops/csaleorderuserprops__getlist.244c2c9f.php). |
| USER\_PROPS\_ID | Код профиля покупателя. |
| ORDER\_PROPS\_ID | Код свойства заказа. |
| NAME | Название свойства заказа. |
| VALUE | Значение свойства заказа, сохраненное в профиле покупателя. |

Новинки документации в соцсетях:
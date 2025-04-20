[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)

GetUserType (доступен с 5.1.0)

GetUserType
===========

```
array
CIBlockProperty::GetUserType(
	string USER_TYPE = false
);Копировать
```

Метод возвращает описание пользовательского типа. Метод статический.

**Примечание**: если параметр USER\_TYPE не задан, то метод вернет массив всех пользовательских типов свойств модуля инфоблоков.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| USER\_TYPE | Идентификатор пользовательского типа |

#### Возвращаемое значение

Массив описывающий пользовательский тип.

#### Смотрите также

* [Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)
* [GetUserTypeDescription](/api_help/iblock/classes/user_properties/GetUserTypeDescription.php)

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockPropertyEnum](/api_help/iblock/classes/ciblockpropertyenum/index.php)

GetByID (доступен с 5.1.2)

GetByID
=======

```
array CIBlockPropertyEnum::GetByID(
	int ID
);Копировать
```

Метод возвращает значения [всех полей](/api_help/iblock/fields.php#fpropertyenum) варианта значения свойства типа "список". Или false, если такой вариант отсутствует. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код варианта значения свойства. |

#### Возвращаемое значение

Массив если такой вариант есть и false если вариант отсутствует.

#### Смотрите также

* [Поля вариантов значения свойств типа "список"](/api_help/iblock/fields.php#fpropertyenum)

Новинки документации в соцсетях:
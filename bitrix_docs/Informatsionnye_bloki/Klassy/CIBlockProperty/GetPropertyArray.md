[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)

GetPropertyArray (доступен с 3.0.3)

GetPropertyArray
================

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
CIBlockProperty::GetPropertyArray(
	ID,
	IBLOCK_ID, 
	bCached = true
);Копировать
```

Технический метод, возвращающий описание свойства с кодом *ID*. Используется в API для построения фильтров по свойствам, для методов создания и изменения элементов. Метод статический.

#### Параметры вызова

| Параметр | Тип | Описание |
| --- | --- | --- |
| ID | int|string | Идентификатор или символьный код требуемого свойства. |
| IBLOCK\_ID | int|string|array | Идентификатор или символьный код инфоблока, или же массив идентификаторов (или символьных кодов) инфоблоков, в которых присутствует свойство с заданным кодом. |
| bCached | bool | Если параметр принимает значение *true*, то данные будут браться из статического кеша (при наличии), в противном случае – из базы.   Если запрос выполняется в базу, то с версии 23.200.0 этот запрос дополнительно кешируется.   Параметр является необязательным, по умолчанию принимает значение *true*. |

#### Возвращаемое значение

Метод возвращает *false* или массив, описывающий свойство. Массив состоит из [полей свойства](/api_help/iblock/fields.php#fproperty) и дополнительных служебных полей, необходимых для построения sql-фильтров по свойствам инфоблоков.

### Смотрите также

* [Поля свойства](/api_help/iblock/fields.php#fproperty)

Новинки документации в соцсетях:
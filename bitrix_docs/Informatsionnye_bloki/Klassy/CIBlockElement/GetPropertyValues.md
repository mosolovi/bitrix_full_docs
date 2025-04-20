[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

GetPropertyValues (с версии 14.0.0)

GetPropertyValues
=================

Включить вкладки

Описание и параметры

Возвращаемое значение

Примеры использования

### Описание и параметры

```
CIBlockElement::GetPropertyValues(
	$IBLOCK_ID, 
	$arElementFilter, 
	$extMode = false, 
	$propertyFilter = array()
);Копировать
```

Метод позволяет получить значения свойств для элементов одного информационного блока, отобранных по фильтру

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| IBLOCK\_ID | ID инфоблока (ЕДИНИЧНОЕ значение). |
| arElementFilter | Фильтр [CIBlockElement::GetList](/api_help/iblock/classes/ciblockelement/getlist.php) для отбора элементов. Ключ IBLOCK\_ID указывать нет необходимости - он будет добавлен внутри метода. |
| *extMode* | Признак возврата расширенного числа полей. Необязательный. |
| *propertyFilter* | Фильтр возвращаемых свойств. необязательный. Может иметь только 1 ключ - ID. Это массив ID возвращаемых свойств. Если пуст - будут возвращены значения всех свойств инфоблока, включая неактивные. |

### Возвращаемое значение

Возвращаемое значение - объект типа `CIBlockPropertyResult`.

Если **$extMode = false**, то возвратятся следующие ключи для каждого значения свойства:

IBLOCK\_ELEMENT\_ID - ID элемента,   
IBLOCK\_PROPERTY\_ID - ID свойства,   
VALUE - строковое значение свойства,   
VALUE\_NUM - цифровое значение свойства (имеет смысл для свойств типа число, список, привязка к элементам, разделам, файловым и производным от них).

Если **$extMode = true**, то дополнительно вернутся ключи:

PROPERTY\_VALUE\_ID - ID записи значения свойства в базе,   
DESCRIPTION - описание значения свойства (если есть).

Результат отсортирован по полю IBLOCK\_ELEMENT\_ID

### Примеры использования

Получить все значения свойств с кодами 10 и 14 активных элементов инфоблока 5

```
$iterator = CIBlockElement::GetPropertyValues(5, array('ACTIVE' => 'Y'), true, array('ID' => array(10, 14)));
while ($row = $iterator->Fetch())
{
	print_r($row);
}Копировать
```

Новинки документации в соцсетях:
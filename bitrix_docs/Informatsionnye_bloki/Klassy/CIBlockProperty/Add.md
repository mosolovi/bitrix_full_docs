[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)

Add (доступен с 3.0.3)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int CIBlockProperty::Add(
	array arFields
);Копировать
```

Метод добавляет новое свойство. Отменить добавление или изменить поля свойства можно в обработчике события [OnBeforeIBlockPropertyAdd](/api_help/iblock/events/onbeforeiblockpropertyadd.php). После добавления нового свойства вызываются обработчики события [OnAfterIBlockPropertyAdd](/api_help/iblock/events/onafteriblockpropertyadd.php). Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...).   Содержит значения [всех полей](/api_help/iblock/fields.php#fproperty) свойства. Кроме того, с помощью поля "VALUES", значением которого должен быть массив структуры  ``` array( 	array( 		"VALUE"=>"значение", 		"DEF"=>"по умолчанию (Y/N)", 		"SORT"=>"индекс сортировки" 		... 	), )Копировать ```  , можно установить варианты выбора для свойств типа "список" (подробнее смотрите метод [CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)::[UpdateEnum()](/api_help/iblock/classes/ciblockproperty/updateenum.php)). |

#### Возвращаемое значение

Метод возвращает ID добавленного свойства, если добавление прошло успешно, при возникновении ошибки метод вернет false, а в свойстве объекта LAST\_ERROR будет содержаться текст ошибки.

### Смотрите также

* [CIBlockProperty::Update](/api_help/iblock/classes/ciblockproperty/update.php)
* [Поля свойства](/api_help/iblock/fields.php#fproperty)
* [OnBeforeIBlockPropertyAdd](/api_help/iblock/events/onbeforeiblockpropertyadd.php)
* [OnAfterIBlockPropertyAdd](/api_help/iblock/events/onafteriblockpropertyadd.php)

### Примеры использования

```
<?
$arFields = Array(
	"NAME" => "Цвет",
	"ACTIVE" => "Y",
	"SORT" => "100",
	"CODE" => "color",
	"PROPERTY_TYPE" => "L",
	"IBLOCK_ID" => 11
);
$arFields["VALUES"][0] = Array(
	"VALUE" => "Красный",
	"DEF" => "N",
	"SORT" => "100"
);
$arFields["VALUES"][1] = Array(
	"VALUE" => "Желтый",
	"DEF" => "N",
	"SORT" => "200"
);
$arFields["VALUES"][2] = Array(
	"VALUE" => "Зеленый",
	"DEF" => "Y",
	"SORT" => "300"
);
$ibp = new CIBlockProperty;
$PropID = $ibp->Add($arFields);
?>Копировать
```

```
//добавление свойства типа "HTML"
$arFields = Array(
	"NAME" => "Итог",
	"ACTIVE" => "Y",
	"SORT" => "600",
	"CODE" => "ITOG",
	"PROPERTY_TYPE" => "S",
	"USER_TYPE" => "HTML", 
	"IBLOCK_ID" => $arParams["IBLOCK_ID"],
);
      
$ibp = new CIBlockProperty;
$PropID = $ibp->Add($arFields);
//для добавления свойства типа "Видео" в массиве arFields должно быть указано:
"PROPERTY_TYPE" => "S",
"USER_TYPE" => "video",Копировать
```

```
//установка параметра "Выводить поле для описания значения" для свойства инфоблока ("WITH_DESCRIPTION" => "Y")
// доступно только для типов свойств:  S - строка, N - число и F - файл
$arFields = Array(
	"NAME" => "Прочее",
	"ACTIVE" => "Y",
	"SORT" => "1700",
	"CODE" => "F_OTHER",
	"PROPERTY_TYPE" => "S",
	"IBLOCK_ID" => $IBLOCK_ID,
	"WITH_DESCRIPTION" => "Y",
);
$iblockproperty = new CIBlockProperty;
$PropertyID = $iblockproperty->Add($arFields);Копировать
```

```
//добавление к инфоблоку свойства типа "Справочник"
$arFields = Array(
	"NAME" => "Производитель",
	"ACTIVE" => "Y",
	"SORT" => "50",
	"CODE" => "PROIZVODITEL",
	"PROPERTY_TYPE" => "S",
	"USER_TYPE" => "directory",
	"IBLOCK_ID" => 888888888888888,//номер вашего инфоблока
	"LIST_TYPE" => "L",
	"MULTIPLE" => "N",
	"USER_TYPE_SETTINGS" => array("size"=>"1", "width"=>"0", "group"=>"N", "multiple"=>"N", "TABLE_NAME"=>"b_producers")
);
$ibp = new CIBlockProperty;
$PropID = $ibp->Add($arFields);
//затем следует в значение свойства вставить значение поля  UF_XML_ID от вашего справочника
CIBlockElement::SetPropertyValuesEx(123188, 888888888888888, array('PROIZVODITEL'=>'000000701'));Копировать
```

Новинки документации в соцсетях:
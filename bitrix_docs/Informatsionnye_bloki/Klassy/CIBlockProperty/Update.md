[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)

Update (доступен с 3.0.3)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool CIBlockProperty::Update(
	int ID,
	array arFields
);Копировать
```

Метод изменяет параметры свойства с кодом *ID*. Перед изменением параметров вызываются обработчики события [OnBeforeIBlockPropertyUpdate](/api_help/iblock/events/onbeforeiblockpropertyupdate.php) из которых можно отменить изменения или переопределить поля. А после изменения параметром вызывается событие [OnAfterIBlockPropertyUpdate](/api_help/iblock/events/onafteriblockpropertyupdate.php). Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | ID изменяемой записи. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/iblock/fields.php#fproperty) изменяемого свойства. Кроме того, с помощью поля "VALUES", значением которого должен быть массив вида Array(Array("VALUE"=>"значение", "DEF"=>"по умолчанию (Y/N)", "SORT"=>"индекс сортировки"),...), можно установить варианты выбора для свойств типа "список" (подробнее смотрите метод [CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)::[UpdateEnum()](/api_help/iblock/classes/ciblockproperty/updateenum.php)). |

**Примечание:** без необходимости не передавайте в *arFields* параметр *IBLOCK\_ID*. Если в *arFields* передается *IBLOCK\_ID* и в инфоблоке включена поддержка свойств для разделов (и умный фильтр), то свойство отвяжется от верхнего раздела и снова привяжется к верхнему разделу.

```
$arFields = Array(
	"IBLOCK_ID"=>"1",
	"SORT" => 2,
);
$ibp = new CIBlockProperty;
if(!$ibp->Update($prop['ID'], $arFields))
	echo $ibp->LAST_ERROR; Копировать
```

Код не только изменит индекс сортировки, но еще добавит привязку к верхнему разделу инфоблока.

  

#### Возвращаемое значение

Метод возвращает true если изменение прошло успешно, при возникновении ошибки метод вернет false, а в свойстве LAST\_ERROR объекта будет содержаться текст ошибки.

**Примечание:** если используются **Инфоблоки 2.0** и изменяется базовый тип свойства, то все текущие значения свойств у существующих элементов очищаются.

### Смотрите также

* [CIBlockProperty::Add](/api_help/iblock/classes/ciblockproperty/add.php)
* [Поля свойства](/api_help/iblock/fields.php#fproperty)
* [OnBeforeIBlockPropertyUpdate](/api_help/iblock/events/onbeforeiblockpropertyupdate.php)
* [OnAfterIBlockPropertyUpdate](/api_help/iblock/events/onafteriblockpropertyupdate.php)

### Примеры использования

Пример 1:

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
$arFields["VALUES"][0] = Array
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
if(!$ibp->Update($ID, $arFields))
	echo $ibp->LAST_ERROR;
?>Копировать
```

Пример 2:

В случае обновления информации в пользовательском типе свойства для сохранения ключа USER\_TYPE\_SETTINGS необходимо указать еще ключ USER\_TYPE с реальным значением. В противном случае ключ USER\_TYPE\_SETTINGS не обновится. Неверными будут следующие варианты:

```
$arFields = array(
	'PROPERTY_TYPE' => 'E',
	'USER_TYPE_SETTINGS' => array(
		'WIDTH' => '10',
		'HEIGHT' => '10',
	),
);
$ibp = new CIBlockProperty();
$ibp->Update($ID, $arFields));Копировать
```

и

```
$arFields = array(
	'PROPERTY_TYPE' => 'E',
	'USER_TYPE_SETTINGS' => array(
		'WIDTH' => '10',
		'HEIGHT' => '10',
	),
	'USER_TYPE' => '',
);
$ibp = new CIBlockProperty();
$ibp->Update($ID, $arFields));Копировать
```

Рабочий вариант:

```
$arFields = array(
	'PROPERTY_TYPE' => 'E',
	'USER_TYPE_SETTINGS' => array(
		'WIDTH' => '10',
		'HEIGHT' => '10',
	),
	'USER_TYPE' => 'xxx'
);
$ibp = new CIBlockProperty();
$ibp->Update($ID, $arFields));Копировать
```

Пример 3:

```
//включить индексацию свойства для поиска
$arFields = Array(
	'SEARCHABLE'=>'Y'
);
$ibp = new CIBlockProperty;
if(!$ibp->Update($prop['ID'], $arFields))
	echo $ibp->LAST_ERROR;Копировать
```

Пример 4:

```
// добавление свойства в умный фильтр: 
$arFields = Array('SMART_FILTER' => 'Y', 'IBLOCK_ID' => 123);
$ibp = new CIBlockProperty();
if(!$ibp->Update($prop['ID'], $arFields))
echo $ibp->LAST_ERROR; 
//IBLOCK_ID в arFields указывать обязательно, иначе свойство не будет включено в умный фильтр, и при этом не выдаст ошибки.
//Чтобы исключить свойство из умного фильтра в arFileds заменить:  'SMART_FILTER'=>'N'Копировать
```

Новинки документации в соцсетях:
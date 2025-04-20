[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

Add (доступен с 3.0.8)

Add
===

Включить вкладки

Описание

Параметры вызова

Примеры использования

### Описание

```
int CIBlockElement::Add(
	array arFields,
	bool bWorkFlow = false,
	bool bUpdateSearch = true,
	bool bResizePictures = false
);Копировать
```

Метод добавляет новый элемент информационного блока. Перед добавлением элемента вызываются обработчики события [OnBeforeIBlockElementAdd](/api_help/iblock/events/onbeforeiblockelementadd.php), из которых можно изменить значения полей или отменить добавление элемента вернув сообщение об ошибке. После добавления элемента вызывается событие [OnAfterIBlockElementAdd](/api_help/iblock/events/onafteriblockelementadd.php). Нестатический метод.

#### Смотрите также

* [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php)
* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[SetPropertyValues()](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php)
* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[SetPropertyValueCode()](/api_help/iblock/classes/ciblockelement/setpropertyvaluecode.php)
* [OnBeforeIBlockElementAdd](/api_help/iblock/events/onbeforeiblockelementadd.php)
* [OnAfterIBlockElementAdd](/api_help/iblock/events/onafteriblockelementadd.php)

  

**Примечание:** если при добавлении свойств в PROPERTY\_VALUES при сохранении элемента инфоблока методом CIBlockElement::Add, происходит подобная ошибка:

```
MySQL Query Error: INS ERT INTO b_iblock_element_property (IBLOCK_ELEMENT_ID, IBLOCK_PROPERTY_ID, VALUE, VALUE_NUM) SEL ECT 323 ,P.ID ,'28' ,28,0000 FR OM b_iblock_property P WHERE ID=42[Column count doesn't match val ue count at row 1]Копировать
```

попробуйте выставить пустое значение в *setlocale( LC\_NUMERIC, '' );*, чтобы PHP использовал точку при форматировании числа, а не запятую.

### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив вида Array("поле"=>"значение", ...), содержащий значения [полей элемента](/api_help/iblock/fields.php#felement) инфоблоков и дополнительно может содержать поле "PROPERTY\_VALUES" - массив со всеми значениями свойств элемента в виде массива Array("код свойства"=>"значение свойства"). Где "код свойства" - числовой или символьный код свойства, "значение свойства" - одиночное значение, либо массив значений если свойство множественное. Дополнительно для сохранения значения свойств см: [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[SetPropertyValues()](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php), [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[SetPropertyValueCode()](/api_help/iblock/classes/ciblockelement/setpropertyvaluecode.php).    **Примечание:** поля с датами задаются в формате сайта. |  |
| bWorkFlow | Вставка в режиме документооборота. Если true и модуль документооборота установлен, то данное добавление будет учтено в журнале изменения элемента. Не обязательный параметр, по умолчанию вставка в режиме документооборота отключена. | 3.1.3 |
| bUpdateSearch | Индексировать элемент для поиска. Для повышения производительности можно отключать этот параметр во время серии добавлений элементов, а после вставки переиндексировать поиск. Не обязательный параметр, по умолчанию элемент после добавления будет проиндексирован в поиске. | 3.2.1 |
| bResizePictures | Использовать настройки инфоблока для обработки изображений. По умоляанию настройки не применяются. Если этот параметр имеет значение true, то к полям PREVIEW\_PICTURE и DETAIL\_PICTURE будут применены правила генерации и масштабирования в соответствии с настройками информационного блока. | 8.0.10 |

#### Возвращаемое значение

Метод возвращает ID добавленного элемента инфоблока, если добавление прошло успешно. При возникновении ошибки метод вернет false, а в свойстве объекта LAST\_ERROR будет содержаться текст ошибки.

### Примеры использования

Пример 1:

```
<?
$el = new CIBlockElement;
$PROP = array();
$PROP[12] = "Белый";  // свойству с кодом 12 присваиваем значение "Белый"
$PROP[3] = 38;        // свойству с кодом 3 присваиваем значение 38
$arLoadProductArray = Array(
	"MODIFIED_BY"    => $USER->GetID(), // элемент изменен текущим пользователем
	"IBLOCK_SECTION_ID" => false,          // элемент лежит в корне раздела
	"IBLOCK_ID"      => 18,
	"PROPERTY_VALUES"=> $PROP,
	"NAME"           => "Элемент",
	"ACTIVE"         => "Y",            // активен
	"PREVIEW_TEXT"   => "текст для списка элементов",
	"DETAIL_TEXT"    => "текст для детального просмотра",
	"DETAIL_PICTURE" => CFile::MakeFileArray($_SERVER["DOCUMENT_ROOT"]."/image.gif")
);
if($PRODUCT_ID = $el->Add($arLoadProductArray))
	echo "New ID: ".$PRODUCT_ID;
else
	echo "Error: ".$el->LAST_ERROR;
?>Копировать
```

Пример 2 (примеры массивов для свойств):

```
//описание массива для свойства типа "Html/Text"
$arrProp = Array();
$arrProp[ID или CODE][0] = Array("VALUE" => Array ("TEXT" => "значение", "TYPE" => "html или text"));
//описание массива для свойства типа "Список"
$arrProp = Array();
$arrProp[ID или CODE] = Array("VALUE" => $ENUM_ID ); //ENUM_ID - это ID значения в списке, его можно получить при помощи: CIBlockPropertyEnum::GetList
//описание массива для свойства типа "Список" множественного выбора
$arrProp = Array();
$arrProp[ID или CODE] = array( $ENUM_ID1, $ENUM_ID2, $ENUM_ID3, $ENUM_ID4);
//пример массива для вставки видео
$PROP["561"] = Array (
	"n0" => Array(
		"VALUE" => Array ("PATH" => "/upload/single_2.flv", "WIDTH" => 400, "HEIGHT" => 300, "TITLE" => "Заголовок видео", "DURATION" => "00:30", "AUTHOR" => "Автор видео", "DATE" => "01.02.2011")
	)
);
//При добавлении нового значения/значений множественного свойство типа "Файл" необходимо использовать ключи вида n0,n1,n2 ... nN . 
Копировать
```

Пример 3:

```
//детальная картинка загружается непосредственно из формы
<?
$el = new CIBlockElement;
$PROP = array();
$PROP[12] = 'Белый';  // свойству с кодом 12 присваиваем значение "Белый"
$PROP[3] = 38; // свойству с кодом 3 присваиваем значение 38
$arLoadProductArray = Array(  
	'MODIFIED_BY' => $GLOBALS['USER']->GetID(), // элемент изменен текущим пользователем  
	'IBLOCK_SECTION_ID' => false, // элемент лежит в корне раздела  
	'IBLOCK_ID' => 18,
	'PROPERTY_VALUES' => $PROP,  
	'NAME' => 'Элемент',  
	'ACTIVE' => 'Y', // активен  
	'PREVIEW_TEXT' => 'текст для списка элементов',  
	'DETAIL_TEXT' => 'текст для детального просмотра',  
	'DETAIL_PICTURE' => $_FILES['DETAIL_PICTURE'] // картинка, загружаемая из файлового поля веб-формы с именем DETAIL_PICTURE
);
if($PRODUCT_ID = $el->Add($arLoadProductArray)) {
	echo 'New ID: '.$PRODUCT_ID;
} else {
	echo 'Error: '.$el->LAST_ERROR;
}
?>Копировать
```

Пример 4:

```
//добавления элемента с установкой для его свойства пары "значение" и "описание" 
$el = new CIBlockElement;
$PROP = array();
$PROP[id_property] =  Array(
	"n0" => Array(
		"VALUE" => "value",
		"DESCRIPTION" => "description")
	);
$arLoadProductArray = Array(
	"IBLOCK_SECTION" => false,
	"IBLOCK_ID" => iblock_id,
	"PROPERTY_VALUES" => $PROP,
	"NAME" => "Элемент",
);
$PRODUCT_ID = id_element;
$res = $el->Update($PRODUCT_ID, $arLoadProductArray);Копировать
```

Пример 5:

```
//получить следующий ID для свойства типа "Счётчик" можно методом CIBlockSequence::GetNext и указать его в методе CIBlockElement:Add
CModule::IncludeModule('iblock'); 
$IBLOCK_ID = 21; 
$PROPERTY_ID = 1223; 
$seq = new CIBlockSequence($IBLOCK_ID, $PROPERTY_ID); 
$el = new CIBlockElement; 
$ID = $el->Add(array( 
	"IBLOCK_ID" => $IBLOCK_ID, 
	"NAME" => "test element", 
	"PROPERTY_VALUES" => array($PROPERTY_ID => $seq->GetNext()) 
)); 
$rs = CIBlockElement::GetList(array(), array("ID" => $ID), false, false, array("ID", "PROPERTY_ABSTRACT_ID")); 
if($ar = $rs->GetNext()) 
	echo 'PRINT_R:<pre style="font:16px Courier">', print_r($ar, 1), '</pre>';Копировать
```

Пример 6:

```
//Если при добавлении элемента надо обязательно заполнять символьный код элемента, то можно не писать свою функцию, а воспользоваться системным методом: 
$params = Array(
	"max_len" => "100", // обрезает символьный код до 100 символов
	"change_case" => "L", // буквы преобразуются к нижнему регистру
	"replace_space" => "_", // меняем пробелы на нижнее подчеркивание
	"replace_other" => "_", // меняем левые символы на нижнее подчеркивание
	"delete_repeat_replace" => "true", // удаляем повторяющиеся нижние подчеркивания
	"use_google" => "false", // отключаем использование google
); 
"CODE" => CUtil::translit("здесь переменная названия элемента", "ru" , $params);Копировать
```

Пример 7:

```
//пример с символьными кодами свойств в массиве PROPERTY_VALUES:  
$arFields = array(
	"ACTIVE" => "Y", 
	"IBLOCK_ID" => 123,
	"IBLOCK_SECTION_ID" => 456,
	"NAME" => "Название элемента",
	"CODE" => "nazvanie-elementa",
	"DETAIL_TEXT" => "Описание элемента",
	"PROPERTY_VALUES" => array(
		"MANUFACTURER" =>"Имя производителя", //Производитель - свойство
		"ARTNUMBER" =>"Артикул товара", //Артикул производителя - свойство
		"MATERIAL" =>"Материал товара" //Материал - свойство
	)
);
$oElement = new CIBlockElement();
$idElement = $oElement->Add($arFields, false, false, true); 
//Необходимо помнить, что если вы указали не все свойства в массиве PROPERTY_VALUES, то остальные свойства могут быть удалены.
//Для обновления элемента гораздо безопаснее использовать CIBlockElement::SetPropertyValueCode.Копировать
```

Пример 8 (как получить значение свойства):

```
//например, можно получить значение счетчика и записать его в базу  
//$iblockId - ID инфоблока
//$propertyId - ID свойства
$seq = new CIBlockSequence($iblockId, $propertyId);
$current_value = $seq->GetNext();
//в $current_value - новое значение, которое можно писать в базу Копировать
```

Новинки документации в соцсетях:
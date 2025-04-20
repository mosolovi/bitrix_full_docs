[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

SetPropertyValues (доступен с 3.0.5)

SetPropertyValues
=================

Включить вкладки

Описание

Параметры вызова

Примеры использования

### Описание

```
CIBlockElement::SetPropertyValues(
	int ELEMENT_ID,
	int IBLOCK_ID,
	array PROPERTY_VALUES,
	string PROPERTY_CODE = false
);Копировать
```

Метод сохраняет значения всех свойств элемента информационного блока. Статический метод.

| **Внимание!** Удалять и обновлять несколько значений файлового свойства можно только одним вызовом, а не несколькими, так как меняются ID значений свойств. Например: |
| --- |
| Подразумевается, что необходимо собрать для 1 свойства типа файл все удаляемые значения (PROPERTY\_VALUE\_ID каждого файла) в массив. Затем производить удаление.  ``` <?php $obElement = \CIBlockElement::GetList( 	[], 	[ 		'ID' => (int)$aElementID, 		'IBLOCK_ID' => (int)$iMainIblockId 	], 	false, 	false, 	[ 		'ID', 		'IBLOCK_ID', 	] ); if ($obFields = $obElement->GetNextElement()) { 	$arProperties = $obFields->GetProperties(); 	if (!empty($arProperties)) { 		/** 		* Собираем файлы для удаления в массив, 		* группируя по свойствам 		*/ 		foreach ($arProperties as $sPropCode => $arPropValues) { 			/** 			* $sPropCode - ключ код свойства, в котором мы ищем удаляемый файл без PROPERTY_ и _VALUE, например PHOTO 			* $arPropValues - PROPERTY_VALUE_ID удаляемого файла 			* $arFiles["FILE_DELETE"] - массив, содержащий ID удаляемых файлов всех свойств 			* $sValue - искомое значение ID 			*/ 			foreach ($arPropValues['VALUE'] as $iKeyValue => $sValue) { 				if (in_array($sValue, $arFiles["FILE_DELETE"]) && $arPropValues['PROPERTY_VALUE_ID'][$iKeyValue] > 0) { 					$arDeleteList[$sPropCode][$arPropValues['PROPERTY_VALUE_ID'][$iKeyValue]] = [ 					'	VALUE' => [ 							'del' => 'Y', 						] 					]; 				} 			} 		} 		/** 		* Если массив для удаления файлов не пустой 		* производим удаление 		*/ 		if (!empty($arDeleteList)) { 			foreach ($arDeleteList as $sPropForDelete => $arDeleteFiles) { 				CIBlockElement::SetPropertyValueCode( 					$aElementID, 					$sPropForDelete, 					$arDeleteFiles 				); 			} 		} 	} }Копировать ``` |

#### Смотрите также

* [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php)
* [CIBlockElement::SetPropertyValueCode](/api_help/iblock/classes/ciblockelement/setpropertyvaluecode.php)

### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ELEMENT\_ID | Код элемента, значения свойств которого необходимо установить. |
| IBLOCK\_ID | Код информационного блока. |
| PROPERTY\_VALUES | Массив значений свойств, в котором коду свойства ставится в соответствие значение свойства.   Если *PROPERTY\_CODE* установлен, то должен содержать одно или массив всех значений свойства (множественное) для заданного элемента.   Если *PROPERTY\_CODE* равен *false*, то *PROPERTY\_VALUES* должен быть вида Array("код свойства1"=>"значения свойства1", ....), где "код свойства" - числовой или символьный код свойства, "значения свойства" - одно или массив всех значений свойства (множественное). При этом массив *PROPERTY\_VALUES* должен содержать полный набор значений свойств для данного элемента, т.е. если в нем будет остутствовать одно из свойств, то все его значения для данного элемента будут удалены.   Это справедливо для всех типов свойств кроме типа **файл**. Файлы надо удалять через массив с параметром "del"=>"Y".   Если свойство типа **файл** множественное, то файл будет удален в случае присутствия параметра del, независимо от принимаемого им значения.   **Примечания**:  * При обновлении нужно задать все свойства элемента, иначе те, которые не заданы, будут сброшены. * Если передаётся массив "свойство"=>"значение", то в качестве значения свойств типа "справочник" нужно указывать внешний код элемента справочника. * Для свойства типа **Список** следует передавать идентификатор значения свойства, а не значение. |
| PROPERTY\_CODE | Код изменяемого свойства. Если этот параметр отличен от false, то изменяется только свойство с таким кодом. Не обязательный параметр, по умолчанию равен false. |

### Примеры использования

Пример 1:

```
<?
$ELEMENT_ID = 18;  // код элемента
$PROPERTY_CODE = "PROP1";  // код свойства
$PROPERTY_VALUE = "Синий";  // значение свойства
// Установим новое значение для данного свойства данного элемента
$dbr = CIBlockElement::GetList(array(), array("=ID"=>$ELEMENT_ID), false, false, array("ID", "IBLOCK_ID"));
if ($dbr_arr = $dbr->Fetch())
{
	$IBLOCK_ID = $dbr_arr["IBLOCK_ID"];
	CIBlockElement::SetPropertyValues($ELEMENT_ID, $IBLOCK_ID, $PROPERTY_VALUE, $PROPERTY_CODE);
}
?>Копировать
```

Пример 2 (код вызова метода для свойства типа "Строка"):

```
$value="text";
CIBlockElement::SetPropertyValueCode("$ELEMENT_ID", "code", $value);
Копировать
```

Пример 3 (код вызова метода для свойства типа "HTML/text"):

```
$value="text";
CIBlockElement::SetPropertyValueCode("$ELEMENT_ID", "code", array("VALUE"=>array("TEXT"=>$value, "TYPE"=>"html")));
Копировать
```

Пример 4 (добавление описания к значению):

```
CIBlockElement::SetPropertyValues ( $PRODUCT_ID, $IBLOCK_ID, array("VALUE"=>$prop_value,"DESCRIPTION"=>$prop_description), $property_name ); 
Копировать
```

Пример 5 (удаление свойства типа "Файл"):

```
CIBlockElement::SetPropertyValuesEx(ELEMENT_ID, IBLOCK_ID, array(PROPERTY_ID => Array ("VALUE" => array("del" => "Y")))); 
Копировать
```

Пример 6:

Если требуется обновить всю карточку товара, включая свойства со значениями множественного типа (вместе с их описанием), то это можно сделать одним вызовом Update. Следует добавить описание (DESCRIPTION) к значениям (VALUE) свойств множественного типа, в PROPERTY\_VALUES прописать числовой или символьный код свойства (множественного типа) и присвоить массив со значениями типа:

```
$arrFields = Array( 
	'PROPERTY_ID_OR_CODE' => Array( 
		Array( 
			"VALUE" => 'value1', 
			"DESCRIPTION" => 'desc for value1' 
		), 
		Array( 
			"VALUE" => 'value2', 
			"DESCRIPTION" => 'desc for value2'  
		) 
	)
);Копировать
```

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

SetPropertyValuesEx (доступен с 6.0.0)

SetPropertyValuesEx
===================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CIBlockElement::SetPropertyValuesEx(
	int ELEMENT_ID,
	int IBLOCK_ID,
	array PROPERTY_VALUES,
	array FLAGS = array()
);Копировать
```

Метод сохраняет значения всех свойств элемента информационного блока. В отличие от [SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php) может не содержать полный набор значений. Значения свойств, неуказанных в массиве PROPERTY\_VALUES, будут сохранены. Этот метод более экономен в количестве запросов к БД. Метод статический.

Метод возвращает *Null*.

Если необходимо сохранить пустое значение для множественного свойства, то используйте значение *false*, так как просто пустой массив не сохранится.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ELEMENT\_ID | Код элемента, значения свойств которого необходимо установить. |
| IBLOCK\_ID | Код информационного блока. Может быть не указан. В этом случае будет прочитан из базы данных по коду элемента. |
| PROPERTY\_VALUES | Массив значений свойств, в котором коду свойства ставится в соответствие значение свойства.   Должен быть вида Array("код свойства1"=>"значения свойства1", ....), где "код свойства" - числовой или символьный код свойства, "значения свойства" - одно или массив всех значений свойства (множественное).   **Примечания**:  * При добавлении значений свойств типа "Файл" поле DESCRIPTION обязательно. * Если передаётся массив "свойство"=>"значение", то в качестве значения свойств типа "справочник" нужно указывать внешний код элемента справочника. * Для свойства типа **Список** следует передавать идентификатор значения свойства, а не значение. * для свойства типа **Привязка к файлу на сервере**, нужно передавать путь к файлу от корня сайта. |
| FLAGS | Необязательный параметр предоставляет информацию для оптимизации выполнения. Может содержать следующие ключи:    * NewElement - можно указать если заведомо известно, что значений свойств у данного элемента нет. Экономит один запрос к БД. * DoNotValidateLists - для свойств типа "список" отключает проверку наличия значений в метаданных свойства. |

### Смотрите также

* [CIBlockElement::SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php)

### Примеры использования

Пример 1:

```
<?
$ELEMENT_ID = 18;  // код элемента
$PROPERTY_CODE = "PROP1";  // код свойства
$PROPERTY_VALUE = "Синий";  // значение свойства
// Установим новое значение для данного свойства данного элемента
CIBlockElement::SetPropertyValuesEx($ELEMENT_ID, false, array($PROPERTY_CODE => $PROPERTY_VALUE));
?>Копировать
```

Пример 2 (изменение немножественного свойства типа HTML/Text):

```
$el_id = 125;
$iblock_id = 45;
$prop[$prop_code] = array('VALUE'=>array('TYPE'=>'HTML', 'TEXT'=>$prop_value));
CIBlockElement::SetPropertyValuesEx($el_id, $iblock_id, $prop);Копировать
```

Пример 3:

```
<input name="MyFile1" type="file" />
<input name="MyFile2" type="file" />
function makeCurentFilesArray($InputFileCode) {
	unset($arFiles, $TMPFILE);
	$arFiles = array();  // Массив всех файлов в свойстве []
	$TMPFILE = array(); // Временный массив для текщего файла
	if(is_array($_FILES[$InputFileCode])) {
		foreach($_FILES[$InputFileCode]['tmp_name'] as $key => $val) {
			if(file_exists($val)) { 
				foreach($_FILES[$InputFileCode] as $namekey => $nameval) {
					$TMPFILE[$namekey] = $nameval[$key];
				}
			$arFiles[] = array('VALUE' => $TMPFILE, 'DESCRIPTION' => $TMPFILE['name']); 
			}
		} 
	} 
	return $arFiles;
}
if (!empty($_FILES['MyFile1'])) $PropFileArr['MyFile1'] = makeCurentFilesArray('MyFile1');   
if (!empty($_FILES['MyFile2'])) $PropFileArr['MyFile2'] = makeCurentFilesArray('MyFile2');
                       
CIBlockElement::SetPropertyValuesEx($Element_ID, $IBlock_ID, $PropFileArr); // Обновляем массив свойств типа файлКопировать
```

Новинки документации в соцсетях:
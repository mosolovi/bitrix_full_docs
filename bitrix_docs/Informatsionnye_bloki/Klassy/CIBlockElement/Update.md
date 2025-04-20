[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

Update (доступен с 3.0.8)

Update
======

Включить вкладки

Описание

Параметры вызова

Примеры использования

### Описание

```
bool 
CIBlockElement::Update(
	int ID,
	array arFields,
	bool bWorkFlow = false,
	bool bUpdateSearch = true,
	bool bResizePictures = false,
	bool bCheckDiskQuota = true
);Копировать
```

Метод изменяет параметры элемента с кодом *ID*. Перед изменением элемента вызываются обработчики события  [OnStartIBlockElementUpdate](/api_help/iblock/events/OnStartIBlockElementUpdate.php) из которых можно изменить значения полей или отменить изменение элемента вернув сообщение об ошибке. После изменения элемента вызывается само событие [OnAfterIBlockElementUpdate](/api_help/iblock/events/onafteriblockelementupdate.php). Нестатический метод.

Если изменяется свойство типа **файл**, то необходимо сформировать [массив](http://dev.1c-bitrix.ru/api_help/main/reference/cfile/makefilearray.php).

#### Смотрите также

* [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php)
* [OnBeforeIBlockElementUpdate](/api_help/iblock/events/onbeforeiblockelementupdate.php)
* [OnAfterIBlockElementUpdate](/api_help/iblock/events/onafteriblockelementupdate.php)

### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | ID изменяемой записи. |  |
| arFields | Массив вида Array("поле"=>"значение", ...), содержащий значения [полей элемента](/api_help/iblock/fields.php#felement) инфоблоков и дополнительно может содержать поле "PROPERTY\_VALUES" - массив со всеми значениями свойств элемента в виде массива Array("код свойства"=>"значение свойства"). Где   "код свойства" - числовой или символьный код свойства,   "значение свойства" - одиночное значение, либо массив значений (если свойство множественное). Если массив *PROPERTY\_VALUES* задан, то он должен содержать полный набор значений свойств для данного элемента, т.е. если в нем будет отсутствовать одно из свойств, то все его значения для данного элемента будут удалены. Это справедливо для всех типов свойств кроме типа **файл**. Файлы надо удалять через массив с параметром "del"=>"Y".   Если свойство типа **список**, то в *PROPERTY\_VALUES* надо отдавать не название, а ID значения.   Дополнительно для сохранения значения свойств см: [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[SetPropertyValues()](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php), [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[SetPropertyValueCode().](/api_help/iblock/classes/ciblockelement/setpropertyvaluecode.php)     **Примечание 1**: нельзя изменить значения полей ID и IBLOCK\_ID.   **Примечание 2**: чтобы при обновлении элемента поле TIMESTAMP\_X не обновилось на текущее время, в arFields необходимо передать:  ``` 'TIMESTAMP_X' => FALSE, // или NULLКопировать ```  **Примечание 3**: Если нужно обновить элемент инфоблока, добавив его в несколько новых разделов, но не изменив "главный", т.е. чтобы URL элемента не изменился, то в вызове CIBlockElement::Update передайте два ключа: IBLOCK\_SECTION\_ID - ID основного раздела, IBLOCK\_SECTION - массив ID всех разделов элемента, включая основной. |  |
| bWorkFlow | Изменение в режиме документооборота. Если true и модуль документооборота установлен, то данное изменение будет учтено в журнале изменений элемента. Не обязательный параметр, по умолчанию изменение в режиме документооборота отключено.   **Примечание:** в режиме документооборота можно передавать значения не всех свойств в PROPERTY\_VALUES, а только необходимых. | 3.1.3 |
| bUpdateSearch | Индексировать элемент для поиска. Для повышения производительности можно отключать этот параметр во время серии изменений элементов, а после их окончания переиндексировать поиск. Не обязательный параметр, по умолчанию элемент после изменения будет автоматически проиндексирован в поиске. | 3.2.1 |
| bResizePictures | Использовать настройки инфоблока для обработки изображений. По умолчанию настройки не применяются. Если этот параметр имеет значение true, то к полям PREVIEW\_PICTURE и DETAIL\_PICTURE будут применены правила генерации и масштабирования в соответствии с настройками информационного блока. | 8.0.10 |
| bCheckDiskQuota | Проверять ограничение по месту занимаемому базой данных и файлами или нет (настройка главного модуля). Необязательный параметр. | 11.0.14 |

#### Возвращаемое значение

Метод возвращает true если изменение прошло успешно, при возникновении ошибки метод вернет false, а в свойстве LAST\_ERROR объекта будет содержаться текст ошибки.

### Примеры использования

```
<?
$el = new CIBlockElement;
$PROP = array();
$PROP[12] = "Белый";  // свойству с кодом 12 присваиваем значение "Белый"
$PROP[3] = 38;        // свойству с кодом 3 присваиваем значение 38
$arLoadProductArray = Array(
	"MODIFIED_BY"    => $USER->GetID(), // элемент изменен текущим пользователем
	"IBLOCK_SECTION" => false,          // элемент лежит в корне раздела
	"PROPERTY_VALUES"=> $PROP,
	"NAME"           => "Элемент",
	"ACTIVE"         => "Y",            // активен
	"PREVIEW_TEXT"   => "текст для списка элементов",
	"DETAIL_TEXT"    => "текст для детального просмотра",
	"DETAIL_PICTURE" => CFile::MakeFileArray($_SERVER["DOCUMENT_ROOT"]."/image.gif")
);
$PRODUCT_ID = 2;  // изменяем элемент с кодом (ID) 2
$res = $el->Update($PRODUCT_ID, $arLoadProductArray);
?>Копировать
```

Менять параметр IBLOCK\_ID нельзя.

Пример задания нового значения дополнительного свойства:

Для типа HTML/TEXT, при вставке HTML-кода и автоматическом подключении HTML-редактора:

```
$PROP[tables] = array("VALUE" => array("TYPE" =>"HTML","TEXT" => $matches[0])); 
Копировать
```

Для типа HTML/TEXT, при вставке plain text:

```
$PROP[tables] = array("VALUE" => array("TYPE" =>"TEXT","TEXT" => $matches[0])); 
Копировать
```

Новинки документации в соцсетях:
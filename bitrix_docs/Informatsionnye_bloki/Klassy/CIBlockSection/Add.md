[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)

Add (доступен с 3.0.6)

Add
===

Включить вкладки

Описание

Параметры вызова

Примеры использования

### Описание

```
int
CIBlockSection::Add(
	array arFields, 
	bool bResort = true,
	bool bUpdateSearch = true,
	bool bResizePictures = false
);Копировать
```

Метод добавляет новый раздел в информационный блок. Перед добавлением раздела вызываются обработчики события [OnBeforeIBlockSectionAdd](/api_help/iblock/events/onbeforeiblocksectionadd.php) из которых можно изменить значения полей или отменить добавление раздела вернув сообщение об ошибке. После добавления раздела вызывается событие [OnAfterIBlockSectionAdd](/api_help/iblock/events/onafteriblocksectionadd.php). Нестатический метод.

#### Смотрите также

* [CIBlockSection::Update](/api_help/iblock/classes/ciblocksection/update.php)
* [OnBeforeIBlockSectionAdd](/api_help/iblock/events/onbeforeiblocksectionadd.php)
* [OnAfterIBlockSectionAdd](/api_help/iblock/events/onafteriblocksectionadd.php)

### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив вида Array("поле"=>"значение", ...), содержащий значения [полей раздела](/api_help/iblock/fields.php#fsection) инфоблоков.    Пользовательские свойства UF\_XXX можно тоже занести в массив и они будут добавляться. |  |
| bResort | Флаг, указывающий пересчитывать ли правую и левую границы после изменения (поля *LEFT\_MARGIN* и *RIGHT\_MARGIN*).    **Примечание**: настоятельно рекомендуется не устанавливать значение *false*. | 3.2.1 |
| bUpdateSearch | Флаг, указывающий, что раздел должен быть проиндексирован для поиска сразу же после сохранения. | 4.0.6 |
| bResizePictures | Использовать настройки инфоблока для обработки изображений. По умолчанию настройки не применяются. Если этот параметр имеет значение true, то к полям PICTURE и DETAIL\_PICTURE будут применены правила генерации и масштабирования в соответствии с настройками информационного блока. | 9.0.4 |

#### Возвращаемое значение

Метод возвращает идентификационный код добавленного раздела блока, если добавление прошло успешно. При возникновении ошибки метод вернет false, а в свойстве объекта LAST\_ERROR будет содержаться текст ошибки.

### Примеры использования

```
<?
$bs = new CIBlockSection;
$arFields = Array(
	"ACTIVE" => $ACTIVE,
	"IBLOCK_SECTION_ID" => $IBLOCK_SECTION_ID,
	"IBLOCK_ID" => $IBLOCK_ID,
	"NAME" => $NAME,
	"SORT" => $SORT,
	"PICTURE" => $_FILES["PICTURE"],
	"DESCRIPTION" => $DESCRIPTION,
	"DESCRIPTION_TYPE" => $DESCRIPTION_TYPE
);
if($ID > 0)
{
	$res = $bs->Update($ID, $arFields);
}
else
{
	$ID = $bs->Add($arFields);
	$res = ($ID>0);
}
if(!$res)
  echo $bs->LAST_ERROR;
?>Копировать
```

Новинки документации в соцсетях:
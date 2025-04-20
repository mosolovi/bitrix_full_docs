[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)

Update (доступен с 3.0.6)

Update
======

Включить вкладки

Описание

Параметры вызова

Примеры использования

### Описание

```
bool CIBlockSection::Update(
	int ID,
	array arFields,
	bool bResort = true,
	bool bUpdateSearch = true,
	bool bResizePictures = false
);Копировать
```

Метод изменяет параметры раздела с кодом *ID*. Перед изменением раздела вызываются обработчики события [OnBeforeIBlockSectionUpdate](/api_help/iblock/events/onbeforeiblocksectionupdate.php) из которых можно изменить значения полей или отменить изменение параметров раздела вернув сообщение об ошибке. После изменения раздела вызывается событие [OnAfterIBlockSectionUpdate](/api_help/iblock/events/onafteriblocksectionupdate.php). Нестатический метод.

**Примечание**: Изменить значения полей GLOBAL\_ACTIVE, DEPTH\_LEVEL, LEFT\_MARGIN, RIGHT\_MARGIN, IBLOCK\_ID, DATE\_CREATE и CREATED\_BY нельзя. Значение первого определяется флагом активности раздела и его родителей. DEPTH\_LEVEL, LEFT\_MARGIN и RIGHT\_MARGIN расчитываются автоматически в зависимости от положения раздела в дереве.

#### Смотрите также

* [CIBlockSection::Add](/api_help/iblock/classes/ciblocksection/add.php)
* [OnBeforeIBlockSectionUpdate](/api_help/iblock/events/onbeforeiblocksectionupdate.php)
* [OnAfterIBlockSectionUpdate](/api_help/iblock/events/onafteriblocksectionupdate.php)

### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Код изменяемой записи. |  |
| arFields | Массив вида Array("поле"=>"значение", ...), содержащий значения [полей раздела](/api_help/iblock/fields.php#fsection) инфоблоков. |  |
| bResort | Флаг, указывающий пересчитывать ли правую и левую границы после изменения (поля *LEFT\_MARGIN* и *RIGHT\_MARGIN*).   **Примечание**: настоятельно рекомендуется не устанавливать значение *false*.   Если в перечне обновляемых полей имеются ключи IBLOCK\_SECTION\_ID, NAME, SORT, ACTIVE, то параметр bResort обязательно должен быть установлен в *true*. В противном случае необходимо вызывать после серии операций метод [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)::[ReSort](/api_help/iblock/classes/ciblocksection/resort.php). |  |
| bUpdateSearch | Флаг, указывающий, что раздел должен быть проиндексирован для поиска сразу же после сохранения. | 4.0.6 |
| bResizePictures | Использовать настройки инфоблока для обработки изображений. По умолчанию настройки не применяются. Если этот параметр имеет значение true, то к полям PICTURE и DETAIL\_PICTURE будут применены правила генерации и масштабирования в соответствии с настройками информационного блока. | 9.0.4 |

#### Возвращаемое значение

Метод возвращает true если изменение прошло успешно, при возникновении ошибки метод вернет false, а в свойстве LAST\_ERROR объекта будет содержаться текст ошибки.

### Примеры использования

```
<?
$bs = new CIBlockSection;
$arPICTURE = $_FILES["PICTURE"];
$arPICTURE["MODULE_ID"] = "iblock";
$arFields = Array(
	"ACTIVE" => $ACTIVE,
	"IBLOCK_SECTION_ID" => $IBLOCK_SECTION_ID,
	"IBLOCK_ID" => $IBLOCK_ID,
	"NAME" => $NAME,
	"SORT" => $SORT,
	"PICTURE" => $arPICTURE,
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
?>Копировать
```

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

Add (доступен с 3.0.3)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
	CIBlock::Add(
	array arFields
);Копировать
```

Метод добавляет новый информационный блок. Модифицировать поля, а также отменить создание инфоблока можно добавив обработчик события [OnBeforeIBlockAdd](/api_help/iblock/events/onbeforeiblockadd.php). После успешного добавления инфоблока вызываются обработчики события [OnAfterIBlockAdd](/api_help/iblock/events/onafteriblockadd.php). Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/iblock/fields.php#fiblock) информационного блока.    Дополнительно в поле SITE\_ID должен находиться массив идентификаторов сайтов, к которым привязан добавляемый информационный блок.    Кроме того, с помощью поля "GROUP\_ID", значением которого должен быть массив соответствий кодов групп правам доступа, можно установить права для разных групп на доступ к информационному блоку(см. [CIBlock](/api_help/iblock/classes/ciblock/index.php)::[SetPermission()](/api_help/iblock/classes/ciblock/setpermission.php)).    Если задано поле "FIELDS", то будут выполнены настройки полей инфоблока (см. [CIBlock::SetFields](/api_help/iblock/classes/ciblock/SetFields.php)).    Кроме того, предусмотрено поле "VERSION", определяющее способ хранения значений свойств элементов инфоблока (1 - в общей таблице | 2 - в отдельной). По умолчанию принимает значение **1**.    Если необходимо добавить инфоблок с поддержкой бизнес-процессов, то следует указать два дополнительных поля: *BIZPROC*, принимающее значение **Y**, и *WORKFLOW*, принимающее значение **N**. |

#### Возвращаемое значение

Метод возвращает код добавленного информационного блока, если добавление прошло успешно, при возникновении ошибки метод вернет false, а в свойстве объекта LAST\_ERROR будет содержаться текст ошибки.

### Смотрите также

* [CIBlock::Update](/api_help/iblock/classes/ciblock/update.php)
* [Поля информационного блока](/api_help/iblock/fields.php#fiblock)
* [OnBeforeIBlockAdd](/api_help/iblock/events/onbeforeiblockadd.php)
* [OnAfterIBlockAdd](/api_help/iblock/events/onafteriblockadd.php)
* [CIBlock::SetFields](/api_help/iblock/classes/ciblock/SetFields.php)

### Примеры использования

```
<?
$arPICTURE = $_FILES["PICTURE"];
$ib = new CIBlock;
$arFields = Array(
	"ACTIVE" => $ACTIVE,
	"NAME" => $NAME,
	"CODE" => $CODE,
	"LIST_PAGE_URL" => $LIST_PAGE_URL,
	"DETAIL_PAGE_URL" => $DETAIL_PAGE_URL,
	"IBLOCK_TYPE_ID" => $type,
	"SITE_ID" => Array("en", "de"),
	"SORT" => $SORT,
	"PICTURE" => $arPICTURE,
	"DESCRIPTION" => $DESCRIPTION,
	"DESCRIPTION_TYPE" => $DESCRIPTION_TYPE,
	"GROUP_ID" => Array("2"=>"D", "3"=>"R")
);
if ($ID > 0)
	$res = $ib->Update($ID, $arFields);
else
{
	$ID = $ib->Add($arFields);
	$res = ($ID>0);
}
?>Копировать
```

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

Update (доступен с 3.0.3)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool CIBlock::Update(
	int ID,
	array arFields
);Копировать
```

Метод изменяет параметры информационного блока с кодом *ID*. Модифицировать поля, а также отменить изменение параметров можно добавив обработчик события [OnBeforeIBlockUpdate](/api_help/iblock/events/onbeforeiblockupdate.php). После успешного добавления инфоблока вызываются обработчики события [OnAfterIBlockUpdate](/api_help/iblock/events/onafteriblockupdate.php). Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | ID изменяемого информационного блока. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/iblock/fields.php#fiblock) информационного блока.   Дополнительно в поле SITE\_ID должен находиться массив идентификаторов сайтов, к которым привязан изменяемый информационный блок.   Кроме того, с помощью поля "GROUP\_ID", значением которого должен быть массив соответствий кодов групп правам доступа, можно установить права для разных групп на доступ к информационному блоку(см. [CIBlock](/api_help/iblock/classes/ciblock/index.php)::[SetPermission()](/api_help/iblock/classes/ciblock/setpermission.php)).   Если задано поле "FIELDS", то будут выполнены настройки полей инфоблока (см. [CIBlock::SetFields](/api_help/iblock/classes/ciblock/SetFields.php)). |

#### Возвращаемое значение

Метод возвращает true если изменение прошло успешно, при возникновении ошибки метод вернет false, а в свойстве LAST\_ERROR объекта будет содержаться текст ошибки.

### Смотрите также

* [CIBlock::Add](/api_help/iblock/classes/ciblock/add.php)
* [Поля информационного блока](/api_help/iblock/fields.php#fiblock)
* [CIBlock::SetFields](/api_help/iblock/classes/ciblock/SetFields.php)
* [OnBeforeIBlockUpdate](/api_help/iblock/events/onbeforeiblockupdate.php)
* [OnAfterIBlockUpdate](/api_help/iblock/events/onafteriblockupdate.php)

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
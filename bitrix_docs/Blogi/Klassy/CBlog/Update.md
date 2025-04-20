[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlog](/api_help/blogs/classes/cblog/index.php)

Update (5.0.2)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CBlog::Update(
	int   ID
	array arFields
);Копировать
```

Метод изменяет параметры блога с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемого блога. |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей блога](/api_help/blogs/fields.php#blog).  Также можно задать уровень доступа на сообщения и комментарии. Для этого необходимо задать массив вида *array("PERMS\_POST" => array("userGroupID" => "Permission"[, ...]), "PERMS\_COMMENT" => array("userGroupID" => "Permission"[, ...]))*, где *userGroupID* - группа пользователей блога, *Permission* - уровень доступа. |

#### Возвращаемое значение

Метод возвращает идентификатор измененного блога, если изменение параметров прошло успешно. Для успешного изменения должно модифицироваться как минимум одно основное поле (например DATE\_UPDATE). При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [Поля блога](/api_help/blogs/fields.php#blog)
* [CBlog](/api_help/blogs/classes/cblog/index.php)::[Add](/api_help/blogs/classes/cblog/add.php)
* [Уровни доступа](/api_help/blogs/constant.php)

### Примеры использования

```
<?
$ID = 1;
$arFields = array(
	"NAME" => 'Блог администратора сайта',
	"DESCRIPTION" => 'В блоге описаны все изменения, происходящие на сайте',
	"=DATE_UPDATE" => $DB->CurrentTimeFunction(),
	"GROUP_ID" => '1',
	"ENABLE_IMG_VERIF" => 'N',
	"EMAIL_NOTIFY" => 'Y',
	"ENABLE_RSS" => "N",
	"URL" => "admin-blog",
	"ACTIVE" => "Y",
	"OWNER_ID" => $USER->GetID()
);
$updateID = CBlog::Update($ID, $arFields);
if(IntVal($updateID)>0)
{
	echo "Блог [".$updateID."] изменен.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
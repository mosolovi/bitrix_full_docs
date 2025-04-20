[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogPost](/api_help/blogs/classes/cblogpost/index.php)

Update (5.0.6)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CBlogPost::Update(
	int   ID
	array arFields
);Копировать
```

Метод изменяет параметры сообщения с идентификатором *ID*. Метод статический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор изменяемого сообщения блога. |  |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей соообщения блога](/api_help/blogs/fields.php#post).  Также можно задать отдельный уровень доступа на сообщение и комментарии. Для этого необходимо задать массив вида:  ``` array( 	"PERMS_POST" =>    array("userGroupID" => "Permission"[, ...]), 	"PERMS_COMMENT" => array("userGroupID" => "Permission"[, ...]) )Копировать ```  где *userGroupID* - группа пользователей блога, *Permission* - уровень доступа. |  |
| bSearchIndex | Необязательный параметр. Значение по умолчанию - "true". | 14.0.0 |

#### Возвращаемое значение

Метод возвращает идентификатор измененного сообщения блога, если изменение параметров прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [Поля сообщения](/api_help/blogs/fields.php#post)
* [CBlogPost](/api_help/blogs/classes/cblogpost/index.php)::[Add](/api_help/blogs/classes/cblogpost/add.php)

### Примеры использования

```
<?
$ID = 1;
$arFields = array(
	"TITLE" => 'Мое первое измененное сообщение в блоге',
	"DETAIL_TEXT" => 'Текст моего первого измененного сообщения в блоге',
	"BLOG_ID" => 1,
	"AUTHOR_ID" => $USER->GetID,
	"DATE_PUBLISH" => '25.08.2007 9:40',
	"PUBLISH_STATUS" => BLOG_PUBLISH_STATUS_PUBLISH,
	"ENABLE_TRACKBACK" => 'N',
	"ENABLE_COMMENTS" => 'Y',
	"PERMS_P" => Array("1" => BLOG_PERMS_DENY, "2" => BLOG_PERMS_DENY),
	"PERMS_C" => Array("1" => BLOG_PERMS_READ, "2" => BLOG_PERMS_WRITE)
);
$updateID = CBlogPost::Update($ID, $arFields);
if(IntVal($updateID)>0)
{
	echo "Сообщение [".$updateID."] изменено.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
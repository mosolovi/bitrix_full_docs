[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogPost](/api_help/blogs/classes/cblogpost/index.php)

Add (5.0.6)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CBlogPost::Add(
	array arFields
);Копировать
```

Метод добавляет новое сообщение в блог. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей сообщения блога](/api_help/blogs/fields.php#post).    Также, можно задать отдельный уровень доступа на сообщение и комментарии. Для этого необходимо задать массив вида  ``` array( 	"PERMS_POST" =>    array("userGroupID" => "Permission"[, ...]), 	"PERMS_COMMENT" => array("userGroupID" => "Permission"[, ...]) )Копировать ```  где *userGroupID* - группа пользователей блога, *Permission* - уровень доступа. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного сообщения, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [CBlogPost](/api_help/blogs/classes/cblogpost/index.php)::[Update](/api_help/blogs/classes/cblogpost/update.php)
* [Поля сообщения](/api_help/blogs/fields.php#post)
* [Уровни доступа](/api_help/blogs/constant.php)

### Примеры использования

```
<?
$CATEGORY_ID = CBlogCategory::Add(array("BLOG_ID" => 1,"NAME" => 'Категория 1'));
$arFields = array(
	"TITLE" => 'Мое первое сообщение в блоге',
	"DETAIL_TEXT" => 'Текст моего первого сообщения в блоге',
	"BLOG_ID" => 1,
	"AUTHOR_ID" => $USER->GetID,
	"=DATE_CREATE" => $DB->GetNowFunction(),
	"DATE_PUBLISH" => '15.08.2007 9:40',
	"PUBLISH_STATUS" => BLOG_PUBLISH_STATUS_PUBLISH,
	"ENABLE_TRACKBACK" => 'N',
	"ENABLE_COMMENTS" => 'Y',
	"CATEGORY_ID" => $CATEGORY_ID,
	"PERMS_P" => Array("1" => BLOG_PERMS_READ, "2" => BLOG_PERMS_READ),
	"PERMS_C" => Array("1" => BLOG_PERMS_READ, "2" => BLOG_PERMS_WRITE)
);
$newID = CBlogPost::Add($arFields);
if(IntVal($newID)>0)
{
	foreach($CATEGORY_ID as $v)
		CBlogPostCategory::Add(Array("BLOG_ID" => 1, "POST_ID" => $newID, "CATEGORY_ID"=>$v));
	echo "Новое сообщение [".$newID."] добавлено.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
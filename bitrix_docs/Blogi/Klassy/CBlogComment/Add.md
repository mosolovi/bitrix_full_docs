[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogComment](/api_help/blogs/classes/cblogcomment/index.php)

Add (7.0.2)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CBlogComment::Add(
	array arFields
);Копировать
```

Метод добавляет новый комментарий к сообщению. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей комментария](/api_help/blogs/fields.php#comment). |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного комментария, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

#### Смотрите также

* [CBlogComment](/api_help/blogs/classes/cblogcomment/index.php)::[Update](/api_help/blogs/classes/cblogcomment/update.php)
* [Поля комментария к сообщению](/api_help/blogs/fields.php#comment)

### Примеры использования

```
<?
$UserIP = CBlogUser::GetUserIP();
$arFields = array(
	"TITLE" => 'Мое первое сообщение в блоге',
	"POST_TEXT" => 'Текст моего первого сообщения в блоге',
	"BLOG_ID" => 1,
	"POST_ID" => 2,
	"PARENT_ID" => 0, //комментарий привязан к сообщению
	"AUTHOR_ID" => $USER->GetID(), //добавляем неанонимный комментарий, 
	//в противном случае необходимо задать AUTHOR_NAME, AUTHOR_EMAIL
	"DATE_CREATE" => ConvertTimeStamp(false, "FULL"), 
	"AUTHOR_IP" => $UserIP[0],
	"AUTHOR_IP1" => $UserIP[1]
);
$newID = CBlogComment::Add($arFields);
if(IntVal($newID)>0)
{
	echo "Новый комментарий [".$newID."] добавлен.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
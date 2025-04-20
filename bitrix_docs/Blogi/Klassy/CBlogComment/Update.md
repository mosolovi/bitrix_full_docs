[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogComment](/api_help/blogs/classes/cblogcomment/index.php)

Update (7.0.2)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CBlogComment::Update(
	int   ID
	array arFields
);Копировать
```

Метод изменяет параметры комментария с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор изменяемого комментария к сообщению. |  |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей комментария к сообщению](/api_help/blogs/fields.php#comment). |  |
| bSearchIndex | Необязательный параметр. Значение по умолчанию - "true". | 14.0.0 |

#### Возвращаемое значение

Метод возвращает идентификатор измененного комментария к сообщению, если изменение параметров прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [CBlogComment](/api_help/blogs/classes/cblogcomment/index.php)::[Add](/api_help/blogs/classes/cblogcomment/add.php)
* [Поля комментария к сообщению](/api_help/blogs/fields.php#comment)

### Примеры использования

```
<?
$ID = 1;
$arFields = array(
	"TITLE" => 'Мое первый измененный комментарий',
	"POST_TEXT" => 'Текст моего первого измененного комментария',
	"BLOG_ID" => 1,
	"POST_ID" => 2
);
$updateID = CBlogComment::Update($ID, $arFields);
if(IntVal($updateID)>0)
{
	echo "Комментарий [".$updateID."] изменен.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
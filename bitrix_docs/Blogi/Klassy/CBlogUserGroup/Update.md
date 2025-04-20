[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUserGroup](/api_help/blogs/classes/cblogusergroup/index.php)

Update (7.1.2)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CBlogUserGroup::Update(
	int   ID
	array arFields
);Копировать
```

Метод изменяет параметры группы пользователей блога с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемой группы пользователей. |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей группы пользователей блога](/api_help/blogs/fields.php#usergroup). |

#### Возвращаемое значение

Метод возвращает идентификатор измененной группы пользователей блога, если изменение параметров прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [Поля группы пользователя блога](/api_help/blogs/fields.php#usergroup)
* [CBlogUserGroup](/api_help/blogs/classes/cblogusergroup/index.php)::[Add](/api_help/blogs/classes/cblogusergroup/add.php)

### Примеры использования

```
<?
$ID = 3;
$arFields = array(
	"NAME" => 'Близкие друзья',
	"BLOG_ID" => 1
);
$updateID = CBlogUserGroup::Update($ID, $arFields);
if(IntVal($updateID)>0)
{
	echo "Группа пользователей [".$updateID."] изменена.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
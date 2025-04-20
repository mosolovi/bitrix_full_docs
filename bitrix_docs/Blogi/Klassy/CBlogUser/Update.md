[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUser](/api_help/blogs/classes/cbloguser/index.php)

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
CBlogUser::Update(
	int   ID
	array arFields
);Копировать
```

Метод изменяет параметры пользователя блога с идентификатором *ID*. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемого пользователя блога. |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей пользователя блога](/api_help/blogs/fields.php#user). |

#### Возвращаемое значение

Метод возвращает идентификатор измененного пользователя блога, если изменение параметров прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [CBlogUser](/api_help/blogs/classes/cbloguser/index.php)::[Add](/api_help/blogs/classes/cbloguser/add.php)
* [Поля пользователя блога](/api_help/blogs/fields.php#user)

### Примеры использования

```
<?
//изменим профайл пользователя блога для текущего пользователя
$arUser = CBlogUser::GetByID($USER->GetID(), BLOG_BY_USER_ID)
$arFields = array(
	"ALIAS" => "Псевдоним текущего пользователя",
	"DESCRIPTION" => "Обычный пользователь сайта с блогом",
	"INTERESTS" => "программирование, PHP, MySQL, Bitrix, Битрикс, Microsoft"
);
$updateID = CBlogUser::Update($arUser["ID"], $arFields);
if(IntVal($updateID)>0)
{
	echo "Информация о пользователе блогов [".$updateID."] изменена.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
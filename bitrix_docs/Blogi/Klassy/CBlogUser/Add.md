[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUser](/api_help/blogs/classes/cbloguser/index.php)

Add (5.0.2)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CBlogUser::Add(
	array arFields
);Копировать
```

Метод добавляет нового пользователя блогов. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей пользователя](/api_help/blogs/fields.php#user). |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного пользователя, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

#### Смотрите также

* [CBlogUser](/api_help/blogs/classes/cbloguser/index.php)::[Update](/api_help/blogs/classes/cbloguser/update.php)
* [Поля пользователя блога](/api_help/blogs/fields.php#user)

### Примеры использования

```
<?
//создадим профайл пользователя блога для текущего пользователя
$arFields = array(
	"USER_ID" => $USER->GetID(),
	"=LAST_VISIT" => $DB->GetNowFunction(),
	"=DATE_REG" => $DB->GetNowFunction(),
	"ALLOW_POST" => "Y",
	"ALIAS" => "Псевдоним пользователя",
	"DESCRIPTION" => "Обычный пользователь сайта с блогом",
	"INTERESTS" => "программирование, PHP, MySQL, Bitrix, Битрикс"
);
$newID = CBlogUser::Add($arFields);
if(IntVal($newID)>0)
{
	echo "Новый пользователь блога [".$newID."] добавлен.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
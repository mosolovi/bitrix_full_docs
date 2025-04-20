[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlog](/api_help/blogs/classes/cblog/index.php)

Add (5.0.2)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CBlog::Add(
	array arFields
);Копировать
```

Метод добавляет новый блог. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей блога](/api_help/blogs/fields.php#blog).  Также можно задать уровень доступа на сообщения и комментарии. Для этого необходимо задать массив вида *array("PERMS\_POST" => array("userGroupID" => "Permission"[, ...]), "PERMS\_COMMENT" => array("userGroupID" => "Permission"[, ...]))*, где *userGroupID* - группа пользователей блога, *Permission* - уровень доступа. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного блога, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [CBlog](/api_help/blogs/classes/cblog/index.php)::[Update](/api_help/blogs/classes/cblog/update.php)
* [Поля блога](/api_help/blogs/fields.php#blog)
* [Уровни доступа](/api_help/blogs/constant.php)

### Примеры использования

```
<?
$arFields = array(
	"NAME" => 'Блог администратора сайта',
	"DESCRIPTION" => 'В блоге описаны все изменения, происходящие на сайте',
	"GROUP_ID" => '1',
	"ENABLE_IMG_VERIF" => 'Y',
	"EMAIL_NOTIFY" => 'Y',
	"ENABLE_RSS" => "Y",
	"URL" => "admin-blog",
	"ACTIVE" => "Y",
	"OWNER_ID" => $USER->GetID()
);
$newID = CBlog::Add($arFields);
if(IntVal($newID)>0)
{
	echo "Новый блог [".$newID."] создан.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
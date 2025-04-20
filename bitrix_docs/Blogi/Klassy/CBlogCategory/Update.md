[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogCategory](/api_help/blogs/classes/cblogcategory/index.php)

Update (7.1.2)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CBlogCategory::Update(
	int   ID
	array arFields
);Копировать
```

Метод изменяет параметры категории с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемой категории. |
| arFields | Массив вида *array("BLOG\_ID"=>"ID блога", "NAME"=>"название категории")*. |

#### Возвращаемое значение

Метод возвращает идентификатор измененной категории, если изменение параметров прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

#### Смотрите также

* [CBlogCategory](/api_help/blogs/classes/cblogcategory/index.php)::[Add](/api_help/blogs/classes/cblogcategory/add.php)

### Примеры использования

```
<?
$ID = 1;
$arFields = array(
	"BLOG_ID" => 1,
	"NAME" => 'Личное'
);
$updateID = CBlogCategory::Update($ID, $arFields);
if(IntVal($updateID)>0)
{
	echo "Категория [".$updateID."] изменена.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
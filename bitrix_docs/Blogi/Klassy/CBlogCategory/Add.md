[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogCategory](/api_help/blogs/classes/cblogcategory/index.php)

Add (7.1.2)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CBlogCategory::Add(
	array arFields
);Копировать
```

Метод добавляет новую категорию. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида *array("BLOG\_ID"=>"значение", "NAME"=>"значение")*. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленной категории, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

#### Смотрите также

* [CBlogCategory](/api_help/blogs/classes/cblogcategory/index.php)::[Update](/api_help/blogs/classes/cblogcategory/update.php)

### Примеры использования

```
<?
$arFields = array(
	"BLOG_ID" => 1,
	"NAME" => "Общая категория"
);
$newID = CBlogCategory::Add($arFields);
if(IntVal($newID)>0)
{
	echo "Новая категория [".$newID."] добавлена.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)

Add (5.9.1)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CBlogSitePath::Add(
	array arFields
);Копировать
```

Метод добавляет новый путь. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида *array("SITE\_ID"=>"значение", "PATH"=>"значение")*. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного пути, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

#### Смотрите также

* [CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)::[Update](/api_help/blogs/classes/cblogsitepath/update.php)

### Примеры использования

```
<?
$arFields = array(
	"SITE_ID" => "ru",
	"PATH" => "/blog/"
);
$newID = CBlogSitePath::Add($arFields);
if(IntVal($newID)>0)
{
	echo "Новый путь [".$newID."] добавлен.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
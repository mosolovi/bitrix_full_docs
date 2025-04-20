[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)

Update (5.9.1)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CBlogSitePath::Update(
	int   ID
	array arFields
);Копировать
```

Метод изменяет параметры пути с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемого пути. |
| arFields | Массив вида *array("SITE\_ID"=>"ID сайта", "PATH"=>"путь")*. |

#### Возвращаемое значение

Метод возвращает идентификатор измененного пути, если изменение параметров прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

#### Смотрите также

* [CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)::[Add](/api_help/blogs/classes/cblogsitepath/add.php)

### Примеры использования

```
<?
$ID = 1;
$arFields = array(
	"SITE_ID" => "ru",
	"PATH" => "/ru/blog/"
);
$updateID = CBlogSitePath::Update($ID, $arFields);
if(IntVal($updateID)>0)
{
	echo "Путь [".$updateID."] изменен.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
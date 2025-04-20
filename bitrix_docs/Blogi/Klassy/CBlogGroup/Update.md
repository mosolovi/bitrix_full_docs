[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogGroup](/api_help/blogs/classes/cbloggroup/index.php)

Update (7.1.2)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CBlogGroup::Update(
	int   ID
	array arFields
);Копировать
```

Метод изменяет параметры группы с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемой группы. |
| arFields | Массив вида *array("SITE\_ID"=>"ID сайта", "NAME"=>"название категории")*. |

#### Возвращаемое значение

Метод возвращает идентификатор измененной группы, если изменение параметров прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

#### Смотрите также

* [CBlogGroup](/api_help/blogs/classes/cbloggroup/index.php)::[Add](/api_help/blogs/classes/cbloggroup/add.php)

### Примеры использования

```
<?
$ID = 1;
$arFields = array(
	"SITE_ID" => "ru",
	"NAME" => "Веселые блоги"
);
$updateID = CBlogGroup::Update($ID, $arFields);
if(IntVal($updateID)>0)
{
	echo "Группа [".$updateID."] изменена.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
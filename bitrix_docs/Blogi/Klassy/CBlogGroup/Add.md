[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogGroup](/api_help/blogs/classes/cbloggroup/index.php)

Add (7.1.2)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CBlogGroup::Add(
	array arFields
);Копировать
```

Метод добавляет новую группу. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида *array("SITE\_ID"=>"значение", "NAME"=>"значение")*. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленной группы, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

#### Смотрите также

* [CBlogGroup](/api_help/blogs/classes/cbloggroup/index.php)::[Update](/api_help/blogs/classes/cbloggroup/update.php)

### Примеры использования

```
<?
$arFields = array(
	"SITE_ID" => "ru",
	"NAME" => "Общая группа"
);
$newID = CBlogGroup::Add($arFields);
if(IntVal($newID)>0)
{
	echo "Новая группа [".$newID."] добавлена.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CChapter](/api_help/learning/classes/cchapter/index.php)

GetByID (доступен с 5.1.0, устарел и удален с 12.0.0)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CChapter::GetByID(
	int ID
);Копировать
```

Возвращает главу по ее коду ID.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор главы. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля главы](/api_help/learning/fields.php#chapter)
* [CChapter](/api_help/learning/classes/cchapter/index.php)::[GetList](/api_help/learning/classes/cchapter/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$CHAPTER_ID = 97;
    
	$res = CChapter::GetByID($CHAPTER_ID);
	if ($arChapter = $res->GetNext())
	{
		echo "Name: ".$arChapter["NAME"];
	}
}
?>Копировать
```

Новинки документации в соцсетях:
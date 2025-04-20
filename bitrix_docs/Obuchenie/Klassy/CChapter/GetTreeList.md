[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CChapter](/api_help/learning/classes/cchapter/index.php)

GetTreeList (доступен с 5.1.0, устарел и удален с 12.0.0)

GetTreeList
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CChapter::GetTreeList(
	int COURSE_ID,
	int CHAPTER_ID = 0
);Копировать
```

Метод возвращает список глав, отсортированный в порядке "полного развернутого дерева".

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| COURSE\_ID | Идентификатор курса. |  |
| CHAPTER\_ID | Идентификатор главы. Необязательный параметр. | 9.5.4 |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CChapter](/api_help/learning/classes/cchapter/index.php)::[GetByID](/api_help/learning/classes/cchapter/getbyid.php)
* [CChapter](/api_help/learning/classes/cchapter/index.php)::[GetList](/api_help/learning/classes/cchapter/getlist.php)
* [CCourse](/api_help/learning/classes/ccourse/index.php)::[GetCourseContent](/api_help/learning/classes/ccourse/getcoursecontent.php)
* [Поля главы](/api_help/learning/fields.php#chapter)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$res = CChapter::GetTreeList($COURSE_ID = 105);
	while ($arChapter = $res->GetNext())
	{
		echo str_repeat("&nbsp;&nbsp;&nbsp;&nbsp;", $arChapter["DEPTH_LEVEL"]);
		echo "+".$arChapter["NAME"]."<br>";
	}
	/*
	The above example will output something similar to:
	+Chapter 1
		+Chapter 1.1
		+Chapter 1.2
	+Chapter 2
	+Chapter 3
		+Chapter 3.1
			+Chapter 3.1.1
	*/
}
?>Копировать
```

Новинки документации в соцсетях:
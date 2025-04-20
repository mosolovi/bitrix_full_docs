[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

GetCourseContent (доступен с 5.0.3)

GetCourseContent
================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CCourse::GetCourseContent(
	int COURSE_ID,
	array arAddSelectFileds = Array("DETAIL_TEXT", "DETAIL_TEXT_TYPE", "DETAIL_PICTURE")
);Копировать
```

Возвращает список активных глав и уроков, отсортированный по возрастанию индекса сортировки. Метод нестатический.

**Примечание**

Возвращаемый список содержит одноименные поля глав и уроков. Обязательные поля списка: ID - идентификатор урока или главы; NAME - название; CHAPTER\_ID - идентификатор родительской главы; SORT - индекс сортировки; DEPTH\_LEVEL - уровень вложенности; TYPE - тип ("LE" - урок, "CH" - глава). Для вывода остальных полей используйте массив *arAddSelectFileds*.
Метод предназначен для вывода "дерева" курса. Если поля "DETAIL\_TEXT", "DETAIL\_TEXT\_TYPE", "DETAIL\_PICTURE" не используются - рекомендуется *arAddSelectFileds* оставлять пустым (arAddSelectFileds = Array()).

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| COURSE\_ID | Идентификатор курса. |  |
| arAddSelectFileds | Массив дополнительных полей. Допустимые поля:  *PREVIEW\_TEXT* - Предварительное описание (анонс);  *PREVIEW\_TEXT\_TYPE* - Тип предварительного описания (text/html);  *PREVIEW\_PICTURE* - Код картинки в таблице файлов для предварительного просмотра (анонса);  *DETAIL\_TEXT\_TYPE* - Тип детального описания (text/html);  *DETAIL\_PICTURE* - Код картинки в таблице файлов для детального просмотра;  *DETAIL\_TEXT* - Детальное описание;  По умолчанию массив arAddSelectFileds = Array("DETAIL\_TEXT", "DETAIL\_TEXT\_TYPE", "DETAIL\_PICTURE"); | 5.1.0 |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [Поля урока](/api_help/learning/fields.php#lesson)
* [Поля главы](/api_help/learning/fields.php#chapter)
* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CLesson](/api_help/learning/classes/clesson/index.php)::[GetList](/api_help/learning/classes/clesson/getlist.php)
* [CChapter](/api_help/learning/classes/cchapter/index.php)::[GetList](/api_help/learning/classes/cchapter/getlist.php)
* [CChapter](/api_help/learning/classes/cchapter/index.php)::[GetTreeList](/api_help/learning/classes/cchapter/gettreelist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$res = CCourse::GetCourseContent($COURSE_ID = 105, Array());
	while ($arContent = $res->GetNext())
	{
		echo str_repeat("&nbsp;&nbsp;&nbsp;&nbsp;", $arContent["DEPTH_LEVEL"]);
		echo ($arContent["TYPE"]=="CH" ? "+": "-").$arContent["NAME"]."<br>";
	}
	/*
	The above example will output something similar to:
	+Chapter 1
		+Chapter 1.1
			-Lesson 1.1.1
		+Chapter 1.2
	+Chapter 2
		-Lesson 2
	+Chapter 3
		+Chapter 3.1
			-Lesson 3.1.1
			-Lesson 3.1.2
			+Chapter 3.1.1
	*/
}
?>Копировать
```

Новинки документации в соцсетях:
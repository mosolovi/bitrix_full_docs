[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CChapter](/api_help/learning/classes/cchapter/index.php)

GetNavChain (доступен с 5.1.0, устарел с 12.0.0)

GetNavChain
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CChapter::GetNavChain(
	int courseId,
	int chapterId
);Копировать
```

Метод возвращает путь по дереву от корня до главы *chapterId*.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| courseId | Идентификатор курса.    До версии 12.0.0 параметр назывался COURSE\_ID. |
| chapterId | Идентификатор главы.   До версии 12.0.0 параметр назывался CHAPTER\_ID. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CChapter](/api_help/learning/classes/cchapter/index.php)::[GetList](getlist.php.html)
* [CChapter](/api_help/learning/classes/cchapter/index.php)::[GetByID](/api_help/learning/classes/cchapter/getbyid.php)
* [Поля главы](/api_help/learning/fields.php#chapter)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 90;
	$CHAPTER_ID = 116;
	$nav = CChapter::GetNavChain($COURSE_ID, $CHAPTER_ID);
	$i = 1;
	while($arChain = $nav->GetNext())
	{
		if ($i > 1) echo " -> ";
		echo $arChain["NAME"];
		$i++;
	}
	/*
	The above example will output something similar to:
    
	Chapter 1 -> Chapter 1.1 -> Chapter 1.1.3 -> Chapter 1.1.2
	$CHAPTER_ID - ID of Chapter 1.1.2;
	*/
}
?>Копировать
```

Новинки документации в соцсетях:
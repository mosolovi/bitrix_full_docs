[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CChapter](/api_help/learning/classes/cchapter/index.php)

GetCount (доступен с 5.1.0, устарел и удален с 12.0.0)

GetCount
========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CChapter::GetCount(
	array arFilter = Array()
);Копировать
```

Возвращает количество глав по заданному фильтру.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Описание фильтра см. в [CChapter::GetList](/api_help/learning/classes/cchapter/getlist.php) |

#### Возвращаемое значение

Число - количество глав.

#### Смотрите также

* [CChapter](/api_help/learning/classes/cchapter/index.php)::[GetList](/api_help/learning/classes/cchapter/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
    
	$cnt = CChapter::GetCount(Array("ACTIVE" => "Y", "COURSE_ID" => $COURSE_ID));
	echo "Number of chapters: ".$cnt;
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
    
	$cnt = CChapter::GetCount(Array("CHECK_PERMISSIONS" => "N", "COURSE_ID" => $COURSE_ID));
	echo "Number of chapters: ".$cnt;
}
?>Копировать
```

Новинки документации в соцсетях:
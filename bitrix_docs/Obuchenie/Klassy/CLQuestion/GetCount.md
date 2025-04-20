[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLQuestion](/api_help/learning/classes/clquestion/index.php)

GetCount (доступен с 5.0.3)

GetCount
========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CLQuestion::GetCount(
	array arFilter = Array()
);Копировать
```

Метод возвращает количество вопросов по заданному фильтру. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Описание фильтра см. в [CLQuestion::GetList](/api_help/learning/classes/clquestion/getlist.php).  По умолчанию вопросы не фильтруются. |

#### Возвращаемое значение

Число - количество вопросов.

#### Смотрите также

* [CLQuestion](/api_help/learning/classes/clquestion/index.php)::[GetList](/api_help/learning/classes/clquestion/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
    
	$cnt = CLQuestion::GetCount(Array("ACTIVE" => "Y", "COURSE_ID" => $COURSE_ID));
	echo "Number of questions: ".$cnt;
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$LESSON_ID = 426;
    
	$cnt = CLQuestion::GetCount(Array("LESSON_ID" => $LESSON_ID));
	echo "Number of questions: ".$cnt;
}
?>Копировать
```

Новинки документации в соцсетях:
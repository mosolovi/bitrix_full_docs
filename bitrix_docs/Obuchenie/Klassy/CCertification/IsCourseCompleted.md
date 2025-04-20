[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCertification](/api_help/learning/classes/ccertification/index.php)

IsCourseCompleted (доступен c 5.1.0)

IsCourseCompleted
=================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CCertification::IsCourseCompleted(
	int STUDENT_ID,
	int COURSE_ID
);Копировать
```

Проверяет, пройден ли курс. Курс считается пройденным, если пройдены все его тесты. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| STUDENT\_ID | Идентификатор студента. |
| COURSE\_ID | Идентификатор курса. |

#### Возвращаемое значение

Метод возвращает *true*, если курс пройден, иначе - *false*.

### Смотрите также

* [CGradeBook](/api_help/learning/classes/cgradebook/index.php)::[GetList](/api_help/learning/classes/cgradebook/getlist.php)
* [CTest](/api_help/learning/classes/ctest/index.php)::[GetList](/api_help/learning/classes/ctest/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$STUDENT_ID = 1;
	$COURSE_ID = 92;
	$done = CCertification::IsCourseCompleted($STUDENT_ID, $COURSE_ID);
	if ($done)
		echo "Course completed";
	else
		echo "Course is not completed";
}
?>Копировать
```

Новинки документации в соцсетях:
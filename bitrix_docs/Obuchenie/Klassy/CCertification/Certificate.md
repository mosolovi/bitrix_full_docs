[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCertification](/api_help/learning/classes/ccertification/index.php)

Certificate (доступен c 5.1.0)

Certificate
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CCertification::Certificate(
	int STUDENT_ID,
	int COURSE_ID
);Копировать
```

Добавляет или изменяет сертификат, если курс был пройден. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| STUDENT\_ID | Идентификатор студента. |
| COURSE\_ID | Идентификатор курса. |

#### Возвращаемое значение

Метод возвращает *true*, если сертификация прошла успешно, иначе - *false*.

### Смотрите также

* [CCertification](/api_help/learning/classes/ccertification/index.php)::[Add](/api_help/learning/classes/ccertification/add.php)
* [CCertification](/api_help/learning/classes/ccertification/index.php)::[Update](/api_help/learning/classes/ccertification/update.php)
* [CTest](/api_help/learning/classes/ctest/index.php)::[GetList](/api_help/learning/classes/ctest/getlist.php)
* [CGradeBook](/api_help/learning/classes/cgradebook/index.php)::[GetList](/api_help/learning/classes/cgradebook/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$STUDENT_ID = 1;
	$COURSE_ID = 92;
	$done = CCertification::Certificate($STUDENT_ID, $COURSE_ID);
	if ($done)
		echo "Success!";
	else
		echo "Course is not completed";
}
?>Копировать
```

Новинки документации в соцсетях:
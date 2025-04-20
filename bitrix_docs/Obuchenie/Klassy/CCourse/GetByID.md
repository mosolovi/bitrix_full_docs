[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

GetByID (доступен с 5.0.3)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CCourse::GetByID(
	int ID
);>Копировать
```

Возвращает поля курса по его коду ID. Учитываются права доступа текущего пользователя. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор курса. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля курса](/api_help/learning/fields.php#course)
* [CCourse](/api_help/learning/classes/ccourse/index.php)::[GetList](/api_help/learning/classes/ccourse/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$course = CCourse::GetByID($COURSE_ID);
	if ($arCourse = $course->GetNext())
	{
		echo $arCourse["NAME"];
	}
}
?>Копировать
```

Новинки документации в соцсетях:
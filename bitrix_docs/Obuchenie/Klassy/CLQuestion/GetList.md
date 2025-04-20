[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLQuestion](/api_help/learning/classes/clquestion/index.php)

GetList (доступен с 5.0.3)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CLQuestion::GetList(
	array arOrder = Array("TIMESTAMP_X"=>"DESC"),
	array arFilter = Array()
);Копировать
```

Возвращает список вопросов по фильтру arFilter, отсортированный в порядке arOrder. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*.  Поле для сортировки может принимать значения:  * **ID** - идентификатор вопроса; * **NAME** - название вопроса; * **ACTIVE** - активность вопроса; * **SORT** - индекс сортировки; * **SELF** - вопрос для самопроверки; * **POINT** - баллы; * **TYPE** - тип вопроса; * **TIMESTAMP\_X** - дата изменения вопроса.  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию сортируется по убыванию даты изменения вопроса. |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор вопроса; * **NAME** - название вопроса (можно искать по шаблону [%\_]); * **SORT** - индекс сортировки; * **ACTIVE** - фильтр по активности (Y|N); * **LESSON\_ID** - идентификатор урока; * **POINT** - баллы; * **COURSE\_ID** - идентификатор курса; * **QUESTION\_TYPE** - тип вопроса (S - одиночный выбор, M - множественный выбор); * **SELF** - вопрос для самопроверки (Y|N).  Перед названием фильтруемого поля может указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.    Необязательный. По умолчанию записи не фильтруются. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CLQuestion](/api_help/learning/classes/clquestion/index.php)::[GetByID](/api_help/learning/classes/clquestion/getbyid.php)
* [Поля вопроса](/api_help/learning/fields.php#question)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$LESSON_ID = 426;
	$res = CLQuestion::GetList(
		Array("TIMESTAMP_X" => "ASC", "SORT"=>"ASC"), 
		Array("LESSON_ID" => $LESSON_ID)
	);
	while ($arQuestion = $res->GetNext())
	{
		echo "Question name: ".$arQuestion["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$res = CLQuestion::GetList(
		Array("SORT"=>"ASC"), 
		Array("ACTIVE" => "Y", "COURSE_ID" => $COURSE_ID)
	);
	while ($arQuestion = $res->GetNext())
	{
		echo "Question name: ".$arQuestion["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$res = CLQuestion::GetList(
		Array("SORT"=>"ASC"), 
		Array("?NAME" => "Site")
	);
	while ($arQuestion = $res->GetNext())
	{
		echo "Question name: ".$arQuestion["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$res = CLQuestion::GetList(
		Array("NAME" => "ASC", "SORT"=>"ASC"), 
		Array("COURSE_ID" => $COURSE_ID, "!SELF" => "Y")
	);
	while ($arQuestion = $res->GetNext())
	{
		echo "Question name: ".$arQuestion["NAME"]."<br>";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
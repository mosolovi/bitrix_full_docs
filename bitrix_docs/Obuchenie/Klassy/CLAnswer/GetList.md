[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLAnswer](/api_help/learning/classes/clanswer/index.php)

GetList (доступен с 5.0.6)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CLAnswer::GetList(
	array arOrder = Array("ID"=>"DESC"),
	array arFilter = Array()
);Копировать
```

Возвращает список ответов по фильтру arFilter, отсортированный в порядке arOrder. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*.  Поле для сортировки может принимать значения:  * **ID** - идентификатор ответа; * **SORT** - индекс сортировки; * **CORRECT** - правильность ответа; * **ANSWER** - текст ответа; * **RAND** - случайный порядок;  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию фильтруется по убыванию идентификатора ответа. |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор ответа; * **SORT** - индекс сортировки; * **QUESTION\_ID** - идентификатор вопроса; * **ANSWER** - текст ответа (можно искать по шаблону [%\_]); * **CORRECT** - правильность ответа (Y|N);  Перед названием фильтруемого поля можно указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.    Необязательный. По умолчанию записи не фильтруются. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CLAnswer](/api_help/learning/classes/clanswer/index.php)::[GetByID](/api_help/learning/classes/clanswer/getbyid.php)
* [Поля ответа](/api_help/learning/fields.php#answer)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$QUESTION_ID = 290;
	$res = CLAnswer::GetList(
		Array("SORT"=>"DESC"), 
		Array("QUESTION_ID" => $QUESTION_ID)
	);
	while ($arAnswer = $res->GetNext())
	{
		echo "Answer name: ".$arAnswer["ANSWER"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$QUESTION_ID = 290;
	$res = CLAnswer::GetList(
		Array("SORT"=>"ASC"), 
		Array("QUESTION_ID" => $QUESTION_ID, "?ANSWER" => "sys")
	);
	while ($arAnswer = $res->GetNext())
	{
		echo "Answer name: ".$arAnswer["ANSWER"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$QUESTION_ID = 290;
	$res = CLAnswer::GetList(
		Array(), 
		Array("QUESTION_ID" => $QUESTION_ID, "CORRECT" => "Y")
	);
	while ($arAnswer = $res->GetNext())
	{
		echo "Answer name: ".$arAnswer["ANSWER"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$QUESTION_ID = 290;
	$res = CLAnswer::GetList(
		Array("TIMESTAMP_X" => "ASC", "SORT"=>"ASC"), 
		Array("QUESTION_ID" => $QUESTION_ID)
	);
	while ($arAnswer = $res->GetNext())
	{
		echo "Answer name: ".$arAnswer["ANSWER"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$QUESTION_ID = 290;
	$res = CLAnswer::GetList(
		Array("RAND"=>""), 
		Array("QUESTION_ID" => $QUESTION_ID)
	);
	while ($arAnswer = $res->GetNext())
	{
		echo "Answer name: ".$arAnswer["ANSWER"]."<br>";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
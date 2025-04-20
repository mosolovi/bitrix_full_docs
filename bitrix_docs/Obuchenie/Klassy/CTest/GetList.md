[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTest](/api_help/learning/classes/ctest/index.php)

GetList (доступен с 5.1.0)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CTest::GetList(
	array arOrder = Array("TIMESTAMP_X"=>"DESC"),
	array arFilter = Array()
);Копировать
```

Возвращает список тестов по фильтру arFilter, отсортированный в порядке arOrder. Учитываются права доступа текущего пользователя. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*.  Поле для сортировки может принимать значения:  * **ID** - идентификатор теста; * **SORT** - индекс сортировки; * **NAME** - название теста; * **SORT** - индекс сортировки; * **TIMESTAMP\_X** - даты изменения теста;  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию сортируется по убыванию даты изменения теста. |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор теста; * **SORT** - индекс сортировки; * **COURSE\_ID** - идентификатор курса; * **ATTEMPT\_LIMIT** - количество попыток; * **TIME\_LIMIT** - ограничение времени прохождения теста (в минутах); * **NAME** - название теста (можно искать по шаблону [%\_]); * **DESCRIPTION** - описание теста (можно искать по шаблону [%\_]); * **ACTIVE** - фильтр по активности (Y|N); * **APPROVED** - автоматическая проверка результатов (Y|N); * **INCLUDE\_SELF\_TEST** - включать вопросы для самопроверки (Y|N); * **RANDOM\_QUESTIONS** - случайный порядок вопросов (Y|N); * **RANDOM\_ANSWERS** - случайный порядок ответов (Y|N); * **QUESTIONS\_FROM** - в тесте участвуют вопросы (A - со всего курса, C - с каждой главы, L - с каждого урока, S - все вопросы с урока); * **QUESTIONS\_FROM\_ID** - в тесте участвуют вопросы из конкретного урока; * **PASSAGE\_TYPE** - Тип прохождения теста. 0 - запретить переход к следующему вопросу без ответа на текущий вопрос, пользователь не может изменять свои ответы; 1 - разрешить переход к следующему вопросу без ответа на текущий вопрос, пользователь не может изменять свои ответы; 3 - разрешить переход к следующему вопросу без ответа на текущий вопрос, пользователь может изменять свои ответы. * **MIN\_PERMISSION** - минимальный уровень доcтупа. По умолчанию "R". Список прав доступа см. в [CCourse::SetPermission](/api_help/learning/classes/ccourse/setpermission.php). * **CHECK\_PERMISSIONS** - проверять уровень доступа. Если установлено значение "N" - права доступа не проверяются.  Перед названием фильтруемого поля может указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.    Необязательный. По умолчанию записи не фильтруются. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CTest](/api_help/learning/classes/ctest/index.php)::[GetByID](/api_help/learning/classes/ctest/getbyid.php)
* [Поля теста](/api_help/learning/fields.php#test)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$res = CTest::GetList(
		Array("SORT"=>"ASC"), 
		Array("ACTIVE" => "Y", "COURSE_ID" => $COURSE_ID)
	);
	while ($arTest = $res->GetNext())
	{
		echo "Test name: ".$arTest["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$res = CTest::GetList(
		Array("SORT"=>"ASC"), 
		Array("?NAME" => "Site")
	);
	while ($arTest = $res->GetNext())
	{
		echo "Test name: ".$arTest["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$res = CTest::GetList(
		Array("NAME" => "ASC", "SORT"=>"ASC"), 
		Array("COURSE_ID" => $COURSE_ID, "APPROVED" => "Y")
	);
	while ($arTest = $res->GetNext())
	{
		echo "Test name: ".$arTest["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$res = CTest::GetList(
		Array("TIMESTAMP_X" => "ASC", "SORT"=>"ASC"), 
		Array("CHECK_PERMISSIONS" => "N", "COURSE_ID" => $COURSE_ID)
	);
	while ($arTest = $res->GetNext())
	{
		echo "Test name: ".$arTest["NAME"]."<br>";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
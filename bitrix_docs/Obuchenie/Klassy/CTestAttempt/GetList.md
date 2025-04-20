[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)

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
CTestAttempt::GetList(
	array arOrder = Array("ID"=>"DESC"),
	array arFilter = Array(),
	array arSelect = Array(),
	array arNavParams = Array()
);Копировать
```

Возвращает список попыток по фильтру **arFilter**,
отсортированный в порядке **arOrder**. Учитываются права доступа
текущего пользователя. Метод статический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*. Поле для сортировки может принимать значения:  * **ID** - идентификатор попытки; * **TEST\_ID** - идентификатор теста; * **STUDENT\_ID** - идентификатор студента ; * **DATE\_START** - дата начала попытки; * **DATE\_END** - дата окончания попытки; * **STATUS** - статус попытки; * **SCORE** - количество баллов; * **MAX\_SCORE** - максимальное количество баллов; * **COMPLETED** - тест пройден; * **QUESTIONS** - количество вопросов; * **USER\_NAME** - имя студента ; * **TEST\_NAME** - название теста.  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию сортируется по убыванию идентификатора попытки. |  |
| arFilter | Массив вида *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор попытки; * **TEST\_ID** - идентификатор теста; * **STUDENT\_ID** - идентификатор студента; * **SCORE** - количество баллов; * **MAX\_SCORE** - максимальное количество баллов; * **QUESTIONS** - количество вопросов; * **STATUS** - статус попытки (B - тестирование началось, D - тест   прерван, F - тест закончен.); * **COMPLETED** - тест пройден (Y|N); * **DATE\_START** - дата начала попытки; * **DATE\_END** - дата окончания попытки; * **USER** - пользователь (возможны сложные условия по полям   пользователя ID, LOGIN, NAME, LAST\_NAME); * **MIN\_PERMISSION** - минимальный уровень доcтупа. По умолчанию   "R". Список прав доступа см. в [CCourse::SetPermission](/api_help/learning/classes/ccourse/setpermission.php). * **CHECK\_PERMISSIONS** - проверять уровень доступа. Если   установлено значение "N" - права доступа не проверяются.  Перед названием фильтруемого поля может указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно   "*значения фильтра*" - одиночное значение или массив.  Необязательный. По умолчанию записи не фильтруются. |  |
| arSelect | Массив полей записей, которые будут возвращены методом.   Значение по умолчанию - пустой массив array() - означает, что будут возвращены все поля основной таблицы запроса. | 9.5.2 |
| arNavParams | Массив настроек постраничной навигации. | 12.5.1 |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)::[GetByID](/api_help/learning/classes/ctestattempt/getbyid.php)
* [Поля попытки](/api_help/learning/fields.php#attempt)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_ID = 45;
	$res = CTestAttempt::GetList(
		Array("ID" => "ASC"), 
		Array("TEST_ID" => $TEST_ID)
	);
	while ($arAttempt = $res->GetNext())
	{
		echo "Attempt ID:".$arAttempt["ID"]."; Date start: ".$arAttempt["DATE_START"]."; Test name: ".$arAttempt["TEST_NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_ID = 45;
	$STUDENT_ID = 3;
	$res = CTestAttempt::GetList(
		Array("SCORE" => "DESC"), 
		Array("CHECK_PERMISSIONS" => "N", "TEST_ID" => $TEST_ID, "STUDENT_ID" => $STUDENT_ID)
	);
	while ($arAttempt = $res->GetNext())
	{
		echo "Attempt ID:".$arAttempt["ID"]."; Date start: ".$arAttempt["DATE_START"]."; Test name: ".$arAttempt["TEST_NAME"]."<br>";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
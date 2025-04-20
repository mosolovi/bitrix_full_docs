[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CGradeBook](/api_help/learning/classes/cgradebook/index.php)

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
CGradeBook::GetList(
	array arOrder = Array("ID"=>"DESC"),
	array arFilter = Array()
);Копировать
```

Возвращает список записей журнала по фильтру arFilter, отсортированный в порядке arOrder. Учитываются права доступа текущего пользователя. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*.  Поле для сортировки может принимать значения:  * **ID** - идентификатор записи; * **TEST\_ID** - идентификатор теста; * **STUDENT\_ID** - идентификатор студента ; * **RESULT** - количество баллов; * **MAX\_RESULT** - максимальное количество баллов; * **COMPLETED** - тест пройден; * **USER\_NAME** - имя студента; * **TEST\_NAME** - название теста.  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию фильтруется по убыванию идентификатора записи журнала. |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор записи; * **TEST\_ID** - идентификатор теста; * **STUDENT\_ID** - идентификатор студента; * **RESULT** - количество баллов; * **MAX\_RESULT** - максимальное количество баллов; * **COMPLETED** - тест пройден (Y|N); * **USER** - пользователь (возможны сложные условия по полям пользователя ID, LOGIN, NAME, LAST\_NAME); * **MIN\_PERMISSION** - минимальный уровень доcтупа. По умолчанию "R". Список прав доступа см. в [CCourse::SetPermission](/api_help/learning/classes/ccourse/setpermission.php). * **CHECK\_PERMISSIONS** - проверять уровень доступа. Если установлено значение "N" - права доступа не проверяются.  Перед названием фильтруемого поля можно указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.    Необязательный. По умолчанию записи не фильтруются. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CGradeBook](/api_help/learning/classes/cgradebook/index.php)::[GetByID](/api_help/learning/classes/cgradebook/getbyid.php)
* [Поля журнала](/api_help/learning/fields.php#gradebook)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_ID = 45;
	$res = CGradebook::GetList(
		Array("ID" => "ASC"), 
		Array("TEST_ID" => $TEST_ID)
	);
	while ($arGradebook = $res->GetNext())
	{
		echo "Student: ".$arGradebook["USER_NAME"]."; Test name: ".$arGradebook["TEST_NAME"]."; Completed: ".$arGradebook["COMPLETED"]."<br>";
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
	$res = CGradebook::GetList(
		Array("ID" => "ASC"), 
		Array("CHECK_PERMISSIONS" => "N", "TEST_ID" => $TEST_ID, "STUDENT_ID" => $STUDENT_ID)
	);
	while ($arGradebook = $res->GetNext())
	{
		echo "Student: ".$arGradebook["USER_NAME"]."; Test name: ".$arGradebook["TEST_NAME"]."; Completed: ".$arGradebook["COMPLETED"]."<br>";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLesson](/api_help/learning/classes/clesson/index.php)

GetList (доступен с 5.1.0, устарел с 12.0.0)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CLesson::GetList(
	array arOrder = Array("TIMESTAMP_X"=>"DESC"),
	array arFilter = Array()
);Копировать
```

Возвращает список уроков по фильтру **arFilter**, отсортированный в порядке **arOrder**. Учитываются права доступа текущего пользователя. Метод статический.

**Примечание:** начиная с версии 12.0.0, метод считается устаревшим. Вместо него для работы с главами/уроками следует использовать метод **CLearnLesson::GetList**.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*. Поле для сортировки может принимать значения:  * **ID** - идентификатор урока; * **NAME** - название урока; * **ACTIVE** - активность урока; * **SORT** - индекс сортировки; * **TIMESTAMP\_X** - дата изменения урока. * **CREATED\_BY** - код пользователя, создавшего урок. * **CHAPTER\_NAME** - название главы, в . * **DATE\_CREATE** - дата создания урока.  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию сортируется по убыванию даты изменения урока. |
| arFilter | Массив вида *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор урока; * **NAME** - название урока (можно искать по шаблону [%\_]); * **SORT** - индекс сортировки; * **ACTIVE** - фильтр по активности (Y|N); * **TIMESTAMP\_X** - дата изменения урока; * **DATE\_CREATE** - дата создания урока; * **CHAPTER\_ID** - идентификатор главы. Для получения списка   родительских глав установите это поле в значение *пусто*; * **COURSE\_ID** - идентификатор курса; * **CREATED\_BY** - код пользователя, создавшего урок; * **DETAIL\_TEXT** - детальное описание (можно искать по шаблону   [%\_]); * **PREVIEW\_TEXT** - предварительное описание (можно искать по   шаблону [%\_]); * **MIN\_PERMISSION** - минимальный уровень доcтупа. По умолчанию   "R". Список прав доступа см. в [CCourse::SetPermission](/api_help/learning/classes/ccourse/setpermission.php). * **CHECK\_PERMISSIONS** - проверять уровень доступа. Если   установлено значение "N" - права доступа не проверяются.  Перед названием фильтруемого поля может указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно   "*значения фильтра*" - одиночное значение или массив.  Необязательный. По умолчанию записи не фильтруются. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CLesson](/api_help/learning/classes/clesson/index.php)::[GetByID](/api_help/learning/classes/clesson/getbyid.php)
* [Поля урока](/api_help/learning/fields.php#lesson)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 8;
	$res = CLesson::GetList(
		Array("SORT"=>"ASC"), 
		Array("ACTIVE" => "Y", "COURSE_ID" => $COURSE_ID)
	);
	while ($arLesson = $res->GetNext())
	{
		echo "Lesson name: ".$arLesson["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$res = CLesson::GetList(
		Array("SORT"=>"ASC"), 
		Array("?NAME" => "Site")
	);
	while ($arLesson = $res->GetNext())
	{
		echo "Lesson name: ".$arLesson["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 8;
	$res = CLesson::GetList(
		Array("NAME" => "ASC", "SORT"=>"ASC"), 
		Array("CHECK_PERMISSIONS" => "N", "COURSE_ID" => $COURSE_ID)
	);
	while ($arLesson = $res->GetNext())
	{
		echo "Lesson name: ".$arLesson["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 8;
	$res = CLesson::GetList(
		Array("NAME" => "ASC", "SORT"=>"ASC"), 
		Array("CHECK_PERMISSIONS" => "N", "CHAPTER_ID" => "", "COURSE_ID" => $COURSE_ID)
	);
	while ($arLesson = $res->GetNext())
	{
		echo "Lesson name: ".$arLesson["NAME"]."<br>";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
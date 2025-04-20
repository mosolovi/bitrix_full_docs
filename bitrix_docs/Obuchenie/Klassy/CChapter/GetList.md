[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CChapter](/api_help/learning/classes/cchapter/index.php)

GetList (доступен с 5.1.0, устарел и удален с 12.0.0)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CChapter::GetList(
	array arOrder = Array("TIMESTAMP_X"=>"DESC"),
	array arFilter = Array(),
	bool bIncCnt = false
);Копировать
```

Возвращает список глав по фильтру arFilter, отсортированный в порядке arOrder. Учитываются права доступа текущего пользователя.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*.  Поле для сортировки может принимать значения:  * **ID** - идентификатор главы; * **NAME** - название главы; * **ACTIVE** - активность главы; * **SORT** - индекс сортировки; * **TIMESTAMP\_X** - дата изменения главы.  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию сортируется по убыванию даты изменения главы. |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор главы; * **NAME** - название главы (можно искать по шаблону [%\_]); * **SORT** - индекс сортировки; * **CODE** - символьное имя главы (можно искать по шаблону [%\_]); * **ACTIVE** - фильтр по активности (Y|N); * **TIMESTAMP\_X** - дата изменения главы; * **CHAPTER\_ID** - идентификатор главы. Для получения списка родительских глав установите это поле в значение *пусто*; * **COURSE\_ID** - идентификатор курса; * **DETAIL\_TEXT** - детальное описание (можно искать по шаблону [%\_]); * **PREVIEW\_TEXT** - предварительное описание (можно искать по шаблону [%\_]); * **MIN\_PERMISSION** - минимальный уровень доcтупа. По умолчанию "R". Список прав доступа см. в [CCourse::SetPermission](/api_help/learning/classes/ccourse/setpermission.php). * **CHECK\_PERMISSIONS** - проверять уровень доступа. Если установлено значение "N" - права доступа не проверяются; * **CNT\_ACTIVE** - считать количество только активных уроков. Работает, если *bIncCnt* установлено в значение *true*.  Перед названием фильтруемого поля может быть указан тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.    Необязательный. По умолчанию записи не фильтруются. |
| bIncCnt | Возвращать ли количество уроков главы в поле *ELEMENT\_CNT*. Не обязательный параметр, по умолчанию равен *false*. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CChapter](/api_help/learning/classes/cchapter/index.php)::[GetByID](/api_help/learning/classes/cchapter/getbyid.php)
* [Поля главы](/api_help/learning/fields.php#chapter)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$res = CChapter::GetList(
		Array("SORT"=>"ASC"), 
		Array("ACTIVE" => "Y", "COURSE_ID" => $COURSE_ID, "CNT_ACTIVE" => "Y"),
		true
	);
	while ($arChapter = $res->GetNext())
	{
		echo "Chapter name: ".$arChapter["NAME"]."<br>";
		echo "Active lessons: ".$arChapter["ELEMENT_CNT"]."<br><br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$res = CChapter::GetList(
		Array("SORT"=>"ASC"), 
		Array("?NAME" => "Site")
	);
	while ($arChapter = $res->GetNext())
	{
		echo "Chapter name: ".$arChapter["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$res = CChapter::GetList(
		Array("NAME" => "ASC", "SORT"=>"ASC"), 
		Array("COURSE_ID" => $COURSE_ID)
	);
	while ($arChapter = $res->GetNext())
	{
		echo "Chapter name: ".$arChapter["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$res = CChapter::GetList(
		Array("TIMESTAMP_X" => "ASC", "SORT"=>"ASC"), 
		Array("CHECK_PERMISSIONS" => "N", "CHAPTER_ID" => "", "COURSE_ID" => $COURSE_ID)
	);
	while ($arChapter = $res->GetNext())
	{
		echo "Chapter name: ".$arChapter["NAME"]."<br>";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
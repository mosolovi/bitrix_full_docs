[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

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
CCourse::GetList(
	array arOrder = array(),
	array arFields = array(),
	array arNavParams = array()
);Копировать
```

Возвращает список курсов, отсортированный в порядке arOrder. Учитываются права доступа текущего пользователя. Метод статический.

#### Параметры метода

| Параметр | Описание | С версии | До версии |
| --- | --- | --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*.  Поле для сортировки может принимать значения:  * **ID** - идентификатор курса; * **NAME** - название курса; * **ACTIVE** - активность курса; * **SORT** - индекс сортировки; * **TIMESTAMP\_X** - дата изменения курса.  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию; |  |  |
| arFields | Фильтр данных. Значения полей см. в **arFilter** ниже. | 12.0.0 |  |
| arNavParams | Массив настроек постраничной навигации. | 14.0.0 |  |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор курса; * **NAME** - название курса (можно искать по шаблону [%\_]); * **SORT** - индекс сортировки; * **CODE** - символьное имя курса (можно искать по шаблону [%\_]); * **DESCRIPTION** - описание курса (можно искать по шаблону [%\_]); * **ACTIVE** - фильтр по активности (Y|N); * **SITE\_ID** - идентификатор сайта; * **TIMESTAMP\_X** - дата изменения курса; * **ACTIVE\_FROM** - дата начала активности с учётом пустого значения; * **ACTIVE\_TO** - дата окончания активности с учётом пустого значения; * **DATE\_ACTIVE\_FROM** - дата начала активности без учета пустого значения; * **DATE\_ACTIVE\_TO** - дата окончания активности без учета пустого значения; * **ACTIVE\_DATE** - непустое значение задействует фильтр по датам активности (ACTIVE\_FROM и ACTIVE\_TO). Если значение не установлено (""), фильтрация по датам активности не производится; * **MIN\_PERMISSION** - минимальный уровень доcтупа. По умолчанию "R". Список прав доступа см. в [CCourse::SetPermission](/api_help/learning/classes/ccourse/setpermission.php). * **CHECK\_PERMISSIONS** - проверять уровень доступа. Если установлено значение "N" - права доступа не проверяются; * **CNT\_ACTIVE** - считать количество только активных уроков. Работает, если *bIncCnt* установлено в значение *true*.  Перед названием фильтруемого поля можно указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.    Необязательный. По умолчанию записи не фильтруются. |  | 12.0.0 |
| bIncCnt | Возвращать ли количество уроков курса в поле *ELEMENT\_CNT*. Необязательный параметр, по умолчанию равен *false*. |  | 12.0.0 |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CCourse](/api_help/learning/classes/ccourse/index.php)::[GetByID](/api_help/learning/classes/ccourse/getbyid.php)
* [Поля курса](/api_help/learning/fields.php#course)

### Примеры использования

```
lt;?
if (CModule::IncludeModule("learning"))
{
	$res = CCourse::GetList(
		Array("SORT"=>"ASC"), 
		Array("ACTIVE" => "Y", "CNT_ACTIVE" => "Y"), 
		$bIncCnt = true
	);
	while ($arCourse = $res->GetNext())
	{
		echo "Course name: ".$arCourse["NAME"]."<br>";
		echo "Active lessons: ".$arCourse["ELEMENT_CNT"]."<br><br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$res = CCourse::GetList(
		Array("SORT"=>"ASC"), 
		Array("?NAME" => "Site")
	);
	while ($arCourse = $res->GetNext())
	{
		echo "Course name: ".$arCourse["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$res = CCourse::GetList(
		Array("NAME" => "ASC", "SORT"=>"ASC"), 
		Array("CHECK_PERMISSIONS" => "N")
	);
	while ($arCourse = $res->GetNext())
	{
		echo "Course name: ".$arCourse["NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if(CModule::IncludeModule("learning")):
	$res = CCourse::GetList(Array("SORT" => "DESC"), Array("ACTIVE" => "Y", "ACTIVE_DATE" => "Y", "SITE_ID" => LANG));
	while ($arElement = $res->GetNext()):?>
		<font class="text">
		<?if ($arElement["PREVIEW_PICTURE"]):?>
			<table cellpadding="0" cellspacing="0" border="0" align="left">
				<tr>
					<td><?echo ShowImage($arElement["PREVIEW_PICTURE"], 200, 200, "hspace='0' vspace='2' align='left' border='0'", "", true);?></td>
					<td valign="top" width="0%"><img src="/bitrix/images/1.gif" width="10" height="1"></td>
				</tr>
			</table>
		<?endif;?>
		<a target="blank_" href="<?=$COURSE_URL?>?COURSE_ID=<?=$arElement["ID"]?>"><?=$arElement["NAME"]?></a>
		<?=(strlen($arElement["PREVIEW_TEXT"])>0 ? "<br>".$arElement["PREVIEW_TEXT"]: "")?>
		</font><br clear="all"><br>
	<?endwhile?>
<?endif?>
?>Копировать
```

Новинки документации в соцсетях:
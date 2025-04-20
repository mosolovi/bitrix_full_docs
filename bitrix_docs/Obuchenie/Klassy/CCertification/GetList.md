[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCertification](/api_help/learning/classes/ccertification/index.php)

GetList (доступен c 5.1.0)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CCertification::GetList(
	array arOrder = Array("ID"=>"DESC"),
	array arFilter = Array()
);Копировать
```

Возвращает список сертификатов по фильтру **arFilter**, отсортированный в порядке **arOrder**. Учитываются права доступа текущего пользователя. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*.   Поле для сортировки может принимать значения:  * **ID** - идентификатор сертификата; * **STUDENT\_ID** - идентификатор студента ; * **COURSE\_ID** - идентификатор курса; * **SUMMARY** - cумма баллов, набранных за прохождение всех тестов курса; * **MAX\_SUMMARY** - максимально возможная сумма баллов за прохождение всех тестов курса; * **SORT** - индекс сортировки; * **ACTIVE** - фильтр по активности (Y|N); * **FROM\_ONLINE** - сертификат получен через online-обучение (Y/N); * **PUBLIC\_PROFILE** - публиковать сертификат в профиле (Y/N); * **DATE\_CREATE** - дата создания сертификата; * **TIMESTAMP\_X** - дата изменения студента.  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию фильтруется по убыванию идентификатора сертификата. |
| arFilter | Массив вида *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор сертификата; * **STUDENT\_ID** - идентификатор студента ; * **COURSE\_ID** - идентификатор курса; * **SUMMARY** - cумма баллов, набранных за прохождение всех тестов курса; * **MAX\_SUMMARY** - максимально возможная сумма баллов за прохождение всех тестов курса; * **SORT** - индекс сортировки; * **ACTIVE** - фильтр по активности (Y|N); * **FROM\_ONLINE** - сертификат получен через online-обучение (Y/N); * **PUBLIC\_PROFILE** - публиковать сертификат в профиле (Y/N); * **DATE\_CREATE** - дата создания сертификата; * **TIMESTAMP\_X** - дата изменения студента. * **USER** - пользователь (возможны сложные условия по полям пользователя ID, LOGIN, NAME, LAST\_NAME); * **MIN\_PERMISSION** - минимальный уровень доступа. По умолчанию "R". Список прав доступа см. в [CCourse::SetPermission](/api_help/learning/classes/ccourse/setpermission.php). * **CHECK\_PERMISSIONS** - проверять уровень доступа. Если установлено значение "N" - права доступа не проверяются.  Перед названием фильтруемого поля можно указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.     Необязательный. По умолчанию записи не фильтруются. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CCertification](/api_help/learning/classes/ccertification/index.php)::[GetByID](/api_help/learning/classes/ccertification/getbyid.php)
* [Поля сертификата](/api_help/learning/fields.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 100;
	$res = CCertification::GetList(
		Array("SUMMARY" => "DESC", "SORT"=>"ASC"), 
		Array("ACTIVE" => "Y", "COURSE_ID" => $COURSE_ID)
	);
	while ($arCertification = $res->GetNext())
	{
		echo "User:".$arCertification["USER_NAME"].
			"; Course name: ".$arCertification["COURSE_NAME"]."<br>";
	}
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 100;
	$res = CCertification::GetList(
		Array("SUMMARY" => "DESC", "SORT"=>"ASC"), 
		Array("ACTIVE" => "Y", "CHECK_PERMISSIONS" => "N")
	);
	while ($arCertification = $res->GetNext())
	{
		echo "User:".$arCertification["USER_NAME"].
		"; Course name: ".$arCertification["COURSE_NAME"]."<br>";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
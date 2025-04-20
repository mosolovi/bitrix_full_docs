[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CStudent](/api_help/learning/classes/cstudent/index.php)

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
CStudent::GetList(
	array arOrder = Array("ID"=>"DESC"),
	array arFilter = Array()
);Копировать
```

Возвращает список учётных записей студентов по фильтру
**arFilter**, отсортированный в порядке
**arOrder**. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*. Поле для сортировки может принимать значения:  * **USER\_ID** - [Код   пользователя](/api_help/main/reference/cuser/index.php); * **PUBLIC\_PROFILE** - профиль доступен публично (Y/N);  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию сортируется по убыванию кода пользователя. |
| arFilter | Массив вида *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **USER\_ID** - [Код   пользователя](/api_help/main/reference/cuser/index.php); * **PUBLIC\_PROFILE** - профиль доступен публично (Y/N); * **TRANSCRIPT** - числовой случайный идентификатор; * **RESUME** - резюме студента (можно искать по шаблону [%\_]);  Перед названием фильтруемого поля можно указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно   "*значения фильтра*" - одиночное значение или массив.  Необязательный. По умолчанию записи не фильтруются. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CStudent](/api_help/learning/classes/cstudent/index.php)::[GetByID](/api_help/learning/classes/cstudent/getbyid.php)
* [Поля студента](/api_help/learning/fields.php#student)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$USER_ID = 1; $TRANSCRIPT = 46785643;
	$res = CStudent::GetList(Array(), Array("USER_ID" => $USER_ID, "TRANSCRIPT" => $TRANSCRIPT));
	while ($arProfile = $res->GetNext())
	{
		echo $arProfile["RESUME"];
	}
}
?>Копировать
```

Новинки документации в соцсетях:
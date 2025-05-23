[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUserGroup](/api_help/blogs/classes/cblogusergroup/index.php)

GetList (7.1.2)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CBlogUserGroup::GetList(
	array arOrder = Array("ID"=>"DESC"),
	array arFilter = Array(),
	bool  arGroupBy = false,
	bool  arNavStartParams = false,
	array arSelectFields = Array()
);Копировать
```

Возвращает список групп пользователей блога по фильтру *arFilter*, отсортированный в порядке *arOrder*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида  *array("поле сортировки"=>"направление сортировки" [, ...])* Поле для сортировки может принимать значения:  * **ID**  - идентификатор группы пользователей; * **NAME**  - название группы пользователей; * **BLOG\_ID**  - идентификатор блога; * **USER2GROUP\_ID**  - идентификатор привязки пользователя к группе пользователей; * **USER2GROUP\_USER\_ID**  - идентификатор пользователя группы пользователей блога.  Необязательный. По умолчанию фильтруется по убыванию идентификатора группы пользователей. |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID**  - идентификатор группы пользователей; * **NAME**  - название группы пользователей; * **BLOG\_ID**  - идентификатор блога; * **USER2GROUP\_ID**  - идентификатор привязки пользователя к группе пользователей; * **USER2GROUP\_USER\_ID**  - идентификатор пользователя группы пользователей блога.  Перед названием фильтруемого поля может указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.    Необязательный. По умолчанию записи не фильтруются. |
| arGroupBy | Массив полей, по которым группируются записи. Массив имеет вид:  ``` array( 	"название_поля1", 	"группирующая_функция2" => "название_поля2", 	... )Копировать ```  В качестве "название\_поля*N*" может стоять любое поле. В качестве группирующей функции могут стоять:  * **COUNT** - подсчет количества; * **AVG** - вычисление среднего значения; * **MIN** - вычисление минимального значения; * **MAX** - вычисление максимального значения; * **SUM** - вычисление суммы.  Если массив пустой, то метод вернет число записей, удовлетворяющих фильтру.    Необязательный. По умолчанию - *false* - означает, что результат группироваться не будет. |
| arNavStartParams | Массив параметров выборки. Может содержать следующие ключи:  * "**nTopCount**" - количество возвращаемых методом записей будет ограничено сверху значением этого ключа * любой ключ, принимаемый методом  **CDBResult::NavQuery** в качестве третьего параметра.  Необязательный. По умолчанию - *false* - означает, что параметров выборки нет. |
| arSelectFields | Массив полей записей, которые будут возвращены методом. Можно указать только те поля, которые необходимы. Если в массиве присутствует значение "\*", то будут возвращены все доступные поля.    Необязательный. По умолчанию - пустой массив array() - означает, что будут возвращены все поля основной таблицы запроса. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля группы пользователей](/api_help/blogs/fields.php#usergroup)

### Примеры использования

```
<?
// выберем все группы пользователей блога с ID = 1
$SORT = Array("NAME" => "ASC", "ID" => "ASC");
$arFilter = Array(
	"BLOG_ID" => 1
);	
$dbUserGroup = CBlogUserGroup::GetList(
	$SORT,
	$arFilter
);
while ($arUserGroup = $dbUserGroup->Fetch())
{
	print_r($arUserGroup);
}
?>Копировать
```

Новинки документации в соцсетях:
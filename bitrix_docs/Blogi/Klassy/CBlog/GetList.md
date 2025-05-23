[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlog](/api_help/blogs/classes/cblog/index.php)

GetList (5.0.2)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CBlog::GetList(
	array arOrder = Array("ID"=>"DESC"),
	array arFilter = Array(),
	bool  arGroupBy = false,
	bool  arNavStartParams = false,
	array arSelectFields = Array()
);Копировать
```

Возвращает список блогов по фильтру *arFilter*, отсортированный в порядке *arOrder*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки результата. Массив вида  *array("поле сортировки"=>"направление сортировки" [, ...])* Поле для сортировки может принимать значения:  * **ID**  - идентификатор блога; * **NAME**  - название блога; * **DATE\_CREATE**  - дата создания блога; * **DATE\_UPDATE**  - дата изменения блога; * **ACTIVE**  - активность блога; * **OWNER\_ID**  - идентификатор владельца блога; * **URL**  - адрес блога; * **GROUP\_ID**  - идентификатор группы блога; * **GROUP\_NAME**  - название группы блога; * **GROUP\_SITE\_ID**  - идентификатор сайта группы блога; * **LAST\_POST\_ID**  - идентификатор последнего сообщения в блоге; * **LAST\_POST\_DATE**  - дата последнего сообщения в блоге; * **OWNER\_LOGIN**  - логин владельца блога; * **OWNER\_NAME**  - имя владельца блога; * **OWNER\_LAST\_NAME**  - фамилия владельца блога; * **OWNER\_EMAIL**  - электронный адрес владельца блога; * **BLOG\_USER\_ALIAS**  - псевдоним владельца блога;  Необязательный. По умолчанию фильтруется по убыванию идентификатора блога. |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID**  - идентификатор блога; * **NAME**  - название блога; * **DATE\_CREATE**  - дата создания блога; * **DATE\_UPDATE**  - дата изменения блога; * **ACTIVE**  - активность блога; * **OWNER\_ID**  - идентификатор владельца блога; * **URL**  - адрес блога; * **GROUP\_ID**  - идентификатор группы блога; * **GROUP\_NAME**  - название группы блога; * **GROUP\_SITE\_ID**  - идентификатор сайта группы блога; * **ENABLE\_COMMENTS**  - включены ли комментарии в блоге; * **ENABLE\_IMG\_VERIF**  - включена ли CAPTCHA для комментариев в блоге; * **EMAIL\_NOTIFY**  - включено ли уведомление по Email в блоге; * **ENABLE\_RSS**  - включен ли экспорт в RSS блога; * **LAST\_POST\_ID**  - идентификатор последнего сообщения в блоге; * **LAST\_POST\_DATE**  - дата последнего сообщения в блоге; * **OWNER\_LOGIN**  - логин владельца блога; * **OWNER\_NAME**  - имя владельца блога; * **OWNER\_LAST\_NAME**  - фамилия владельца блога; * **OWNER\_EMAIL**  - электронный адрес владельца блога; * **BLOG\_USER\_ALIAS**  - псевдоним владельца блога;  Перед названием фильтруемого поля может указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.    Необязательный. По умолчанию записи не фильтруются. |
| arGroupBy | Массив полей, по которым группируются записи. Массив имеет вид:  ``` array( 	"название_поля1", 	"группирующая_функция2" => "название_поля2", 	... )Копировать ```  В качестве "название\_поля*N*" может стоять любое поле. В качестве группирующей функции могут стоять:  * **COUNT** - подсчет количества; * **AVG** - вычисление среднего значения; * **MIN** - вычисление минимального значения; * **MAX** - вычисление максимального значения; * **SUM** - вычисление суммы.  Если массив пустой, то метод вернет число записей, удовлетворяющих фильтру.    Необязательный. По умолчанию - *false* - означает, что результат группироваться не будет. |
| arNavStartParams | Массив параметров выборки. Может содержать следующие ключи:  * "**nTopCount**" - количество возвращаемых методом записей будет ограничено сверху значением этого ключа * любой ключ, принимаемый методом  **CDBResult::NavQuery** в качестве третьего параметра.  Необязательный. По умолчанию - *false* - означает, что параметров выборки нет. |
| arSelectFields | Массив полей записей, которые будут возвращены методом. Можно указать только те поля, которые необходимы. Если в массиве присутствует значение "\*", то будут возвращены все доступные поля.    Необязательный. По умолчанию - пустой массив array() - означает, что будут возвращены все поля основной таблицы запроса. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля блога](/api_help/blogs/fields.php#blog)

### Примеры использования

```
<?
// выберем все активные блоги, привязанные к текущему сайту.
// результат будет отсортирован сначала по дате создания, затем по названию блога
// выберутся только необходимые нам поля: Идентификатор блога, Название блога, Адрес блога,
// Идентификатор владельца блога и Дату создания блога
$SORT = Array("DATE_CREATE" => "DESC", "NAME" => "ASC");
$arFilter = Array(
	"ACTIVE" => "Y",
	"GROUP_SITE_ID" => SITE_ID
);	
$arSelectedFields = array("ID", "NAME", "DESCRIPTION", "URL", "OWNER_ID", "DATE_CREATE");
$dbBlogs = CBlog::GetList(
	$SORT,
	$arFilter,
	false,
	false,
	$arSelectedFields
);
while ($arBlog = $dbBlogs->Fetch())
{
	print_r($arBlog);
}
?>Копировать
```

Новинки документации в соцсетях:
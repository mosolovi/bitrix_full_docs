[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormField](/api_help/form/classes/cformfield/index.php)

GetList (4.0.4)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CFormField::GetList(
	int form_id,
	string get_only_fields,
	string &by = "s_sort",
	string &order = "asc",
	array filter = array(),
	bool &is_filtered
)Копировать
```

Возвращает список [вопросов](/api_help/form/terms.php#question)/[полей](/api_help/form/terms.php#field) веб-формы в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *form\_id* | ID веб-формы. |
| *get\_only\_fields* | Может принимать следующие значения:  * **Y** - возвращаемый список должен содержать только [поля](/api_help/form/terms.php#field) веб-формы; * **N** - возвращаемый список должен содержать только [вопросы](/api_help/form/terms.php#question) веб-формы; * **ALL** - возвращаемый список должен содержать и [вопросы](/api_help/form/terms.php#question) и [поля](/api_help/form/terms.php#field) веб-формы. |
| *by* | Ссылка на переменную с полем для сортировки результирующего списка, может принимать значения:  * **s\_id** - ID; * **s\_active** - флаг активности; * **s\_sid** - символьный идентификатор; * **s\_sort** - индекс сортировки; * **s\_title** - текст [вопроса](/api_help/form/terms.php#question) или заголовок [поля](/api_help/form/terms.php#field) веб-формы; * **s\_comments** - служебный комментарий; * **s\_required** - флаг обязательности ответа на [вопрос](/api_help/form/terms.php#question) веб-формы; * **s\_in\_results\_table** - флаг включения в HTML таблицу результатов; * **s\_in\_excel\_table** - флаг включения в Excel таблицу результатов; * **s\_field\_type** - тип [поля](/api_help/form/terms.php#field) веб-формы. |
| *оrder* | Ссылка на переменную с порядком сортировки, может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию. |
| *filter* | Массив для фильтрации. Необязательный параметр. В массиве допустимы следующие ключи:  * **ID**\* - ID [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) (по умолчанию будет искаться точное совпадение); * **ID\_EXACT\_MATCH** - если значение равно "N", то при фильтрации по **ID** будет искаться вхождение; * **SID**\* - символьный идентификатор [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) (по умолчанию будет искаться точное совпадение); * **SID\_EXACT\_MATCH** - если значение равно "N", то при фильтрации по **SID** будет искаться вхождение; * **TITLE**\* - текст [вопрос](/api_help/form/terms.php#question) или заголовок [поля](/api_help/form/terms.php#field) веб-формы (по умолчанию будет искаться вхождение); * **TITLE\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **TITLE** будет искаться точное совпадение; * **COMMENTS**\* - служебный комментарий (по умолчанию будет искаться вхождение); * **COMMENTS\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **COMMENTS** будет искаться точное совпадение; * **ACTIVE** - флаг активности [Y|N] * **IN\_RESULTS\_TABLE** - флаг включения в HTML таблицу результатов [Y|N]; * **IN\_EXCEL\_TABLE** - флаг включения в Excel таблицу результатов [Y|N]; * **IN\_FILTER** - флаг включения в HTML таблицу результатов [Y|N]; * **REQUIRED** - флаг обязательности ответа на [вопрос](/api_help/form/terms.php#question) веб-формы [Y|N].  \* - допускается сложная логика |
| *is\_filtered* | Ссылка на переменную, хранящую флаг отфильтрованности результирующего списка. Если значение равно "true", то список был отфильтрован. |

### Смотрите также

* [Поля CFormField](/api_help/form/classes/cformfield/index.php)
* [CFormField::GetByID](/api_help/form/classes/cformfield/getbyid.php)
* [CFormField::GetBySID](/api_help/form/classes/cformfield/getbysid.php)

### Примеры использования

```
<?
$FORM_ID = 4; // ID веб-формы
// сформируем массив фильтра
$arFilter = Array(
	"ID"                    => "140 | 141",     // вопрос с ID=140 или с ID=141
	"ID_EXACT_MATCH"        => "Y",             // точное совпадение при фильтрации по ID
	"SID"                   => "VS_BIRTHDAY",   // символьный идентификатор
	"SID_EXACT_MATCH"       => "Y",             // точное совпадение с симв. идентификатором
	"TITLE"                 => "День рождения", // текст вопроса
	"TITLE_EXACT_MATCH"     => "N",             // вхождение при фильтрации по тексту вопроса
	"ACTIVE"                => "Y",             // флаг активности
	"IN_RESULTS_TABLE"      => "Y",             // флаг вхождение в HTML таблицу результатов
	"IN_EXCEL_TABLE"        => "N",             // флаг вхождения в Excel таблицу результатов
	"IN_FILTER"             => "Y",             // флаг вхождения в фильтр
	"REQUIRED"              => "Y",             // флаг обязательности ответа на вопрос
);
// получим список всех вопросов веб-формы #4
$rsQuestions = CFormField::GetList(
	$FORM_ID, 
	"N", 
	$by="s_id", 
	$order="desc", 
	$arFilter, 
	$is_filtered
);
while ($arQuestion = $rsQuestions->Fetch())
{
	echo "<pre>"; print_r($arQuestion); echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях:
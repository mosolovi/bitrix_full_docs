[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormAnswer](/api_help/form/classes/cformanswer/index.php)

GetList (4.0.4)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult CFormAnswer::GetList(
	int question_id,
	string &by = "s_sort",
	string &order = "asc",
	array filter = array(),
	bool &is_filtered
)Копировать
```

Возвращает список [ответов](/api_help/form/terms.php#answer) в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *question\_id* | ID [вопроса](/api_help/form/terms.php#question). |
| *by* | Ссылка на переменную с полем для сортировки результирующего списка. Может принимать значения:  * **s\_id** - ID [ответа](/api_help/form/terms.php#answer); * **s\_sort** - индекс сортировки. |
| *оrder* | Ссылка на переменную с порядком сортировки. Может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию. |
| *filter* | Массив для фильтрации. Необязательный параметр. В массиве допустимы следующие ключи:  * **ID**\* - ID [ответа](/api_help/form/terms.php#answer) (по умолчанию будет искаться точное совпадение); * **ID\_EXACT\_MATCH** - если значение равно "N", при фильтрации по **ID** будет искаться вхождение; * **ACTIVE** - флаг активности, допустимые следующие значения:   + **Y** - [ответ](/api_help/form/terms.php#answer) активен;   + **N** - [ответ](/api_help/form/terms.php#answer) не активен. * **MESSAGE**\* - параметр ANSWER\_TEXT (по умолчанию будет искаться вхождение); * **MESSAGE\_EXACT\_MATCH** - если значение равно "Y", при фильтрации по **MESSAGE** будет искаться точное совпадение; * **VALUE**\* - параметр ANSWER\_VALUE (по умолчанию будет искаться вхождение); * **VALUE\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **VALUE** будет искаться точное совпадение; * **FIELD\_TYPE**\* - [тип поля ответа](/api_help/form/classes/cformanswer/index.php#field_type) (по умолчанию будет искаться вхождение); * **FIELD\_TYPE\_EXACT\_MATCH** - если значение равно "Y", при фильтрации по **FIELD\_TYPE** будет искаться точное совпадение; * **FIELD\_PARAM**\* - параметр поля ответа (по умолчанию будет искаться вхождение); * **FIELD\_PARAM\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **FIELD\_PARAM** будет искаться точное совпадение.  \* - допускается [сложная логика](http://dev.1c-bitrix.ru/user_help/general/filter.php) |
| *is\_filtered* | Ссылка на переменную, хранящую флаг отфильтрованности результирующего списка. Если значение равно "true", то список был отфильтрован. |

### Смотрите также

* [Поля CFormAnswer](/api_help/form/classes/cformanswer/index.php)
* [CFormAnswer::GetByID](/api_help/form/classes/cformanswer/getbyid.php)

### Примеры использования

```
<?
$QUESTION_ID = 143; // ID вопроса
// сформируем массив фильтра
$arFilter = Array(
	"ID"                      => "589 | 590", // ID ответа равен 589 или 590
	"ID_EXACT_MATCH"          => "Y",         // точное совпадение для ID
	"ACTIVE"                  => "Y",         // флаг активности
	"MESSAGE"                 => "да | нет",  // параметр ANSWER_TEXT равен "да" или "нет"
	"MESSAGE_EXACT_MATCH"     => "Y",         // точное совпадение для MESSAGE
	"FIELD_TYPE"              => "radio",     // тип поля ответа - radio-кнопка
	"FIELD_TYPE_EXACT_MATCH"  => "Y",         // точное совпадение для FIELD_TYPE
	"FIELD_PARAM"             => "checked",   // параметр включает в себя строку "checked"
	"FIELD_PARAM_EXACT_MATCH" => "N"          // вхождение для FIELD_PARAM
);
// получим список всех ответов вопроса #143
$rsAnswers = CFormAnswer::GetList(
	$QUESTION_ID, 
	$by="s_id", 
	$order="desc", 
	$arFilter, 
	$is_filtered
);
while ($arAnswer = $rsAnswers->Fetch())
{
	echo "<pre>"; print_r($arAnswer); echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях:
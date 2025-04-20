[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormStatus](/api_help/form/classes/cformstatus/index.php)

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
CFormStatus::GetList(
	int form_id,
	string &by = "s_sort",
	string &order = "asc",
	array filter = array(),
	bool &is_filtered
)Копировать
```

Возвращает список [статусов](/api_help/form/terms.php#status) в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *form\_id* | ID [веб-формы](/api_help/form/terms.php#form). |
| *by* | Ссылка на переменную с полем для сортировки результирующего списка, может принимать значения:  * **s\_id** - ID [статуса](/api_help/form/terms.php#status); * **s\_sort** - индекс сортировки; * **s\_timestamp** - время последнего изменения [статуса](/api_help/form/terms.php#status); * **s\_active** - флаг активности; * **s\_default** - флаг установки по умолчанию; * **s\_title** - заголовок; * **s\_description** - описание; * **s\_results** - количество результатов находящихся в данном [статусе](/api_help/form/terms.php#status). |
| *оrder* | Ссылка на переменную с порядком сортировки, может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию. |
| *filter* | Массив для фильтрации. Необязательный параметр. В массиве допустимы следующие ключи:  * **ID**\* - ID [статуса](/api_help/form/terms.php#status) (по умолчанию будет искаться точное совпадение); * **ID\_EXACT\_MATCH** - если значение равно "N", при фильтрации по **ID** будет искаться вхождение; * **ACTIVE** - флаг активности, допустимые следующие значения:   + **Y** - [статус](/api_help/form/terms.php#status) активен;   + **N** - [статус](/api_help/form/terms.php#status) не активен. * **TITLE**\* - заголовок [статуса](/api_help/form/terms.php#status) (по умолчанию будет искаться вхождение); * **TITLE\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **TITLE** будет искаться точное совпадение; * **DESCRIPTION**\* - описание [статуса](/api_help/form/terms.php#status) (по умолчанию будет искаться вхождение); * **DESCRIPTION\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **DESCRIPTION** будет искаться точное совпадение.  \* - допускается сложная логика |
| *is\_filtered* | Ссылка на переменную хранящую флаг отфильтрованности результирующего списка. Если значение равно "true", то список был отфильтрован. |

### Смотрите также

* [Поля CFormStatus](/api_help/form/classes/cformstatus/index.php)
* [CFormStatus::GetByID](/api_help/form/classes/cformstatus/getbyid.php)

### Примеры использования

```
<?
$FORM_ID = 4; // ID веб-формы
// сформируем массив фильтра
$arFilter = Array(
	"ID"                       => "1 | 4",       // ID статуса равен 1 или 4
	"ID_EXACT_MATCH"           => "Y",           // точное совпадение для ID
	"ACTIVE"                   => "Y",           // флаг активности
	"TITLE"                    => "опубликован", // заголовок
	"TITLE_EXACT_MATCH"        => "N",           // точное совпадение для TITLE
	"DESCRIPTION"              => "конечный",    // описание
	"DESCRIPTION_EXACT_MATCH"  => "N",           // точное совпадение для DESCRIPTION
);
// получим список всех статусов формы, соответствующих фильтру
$rsStatuses = CFormStatus::GetList(
	$FORM_ID, 
	$by="s_id", 
	$order="desc", 
	$arFilter, 
	$is_filtered
);
while ($arStatus = $rsStatuses->Fetch())
{
	echo "<pre>"; print_r($arStatus); echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях:
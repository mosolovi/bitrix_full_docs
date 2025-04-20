[Техподдержка](/api_help/support/index.php)

[Классы](/api_help/support/classes/index.php)

[CTicketDictionary](/api_help/support/classes/cticketdictionary/index.php)

GetList (3.0.1)

GetList
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
record set
CTicketDictionary::GetList(
	varchar &by,
	varchar &order,
	array arFilter=array(),
	boolean &is_filtered
);Копировать
```

Метод предназначен для получения списка записей справочника. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| **by** | Идентификатор позволяющий задать имя поля для сортировки. Допустимы следующие значения:  * s\_id - по ID * s\_c\_sort - по указанному порядку сортировки * s\_sid - по символьному коду * s\_lis - по языку * s\_name - по имени * s\_responsible - по ID ответственного * s\_dropdown - по указанному порядку сортировки и по имени |
| **order** | Порядок сортировки. Допустимы следующие значения:  * desc - по убыванию (значение по умолчанию) * asc - по возрастанию |
| **arFilter** | Массив для фильтрации значений. В массиве допустимы следующие индексы:  * ID - ID записи (допускается сложная логика) * SID - символьный код (допускается сложная логика) * LID - ID сайта * TYPE - тип записи: "C" - категория, "K" - критичность, "S" - статус, "M" - оценка ответов, "F" - часто используемые ответы, "SR" - источник * NAME - имя (допускается сложная логика) * RESPONSIBLE\_ID - ID ответственного * RESPONSIBLE - ответственный, поиск осуществляется по ID пользователя, логину, имени, фамилии (допускается сложная логика) * DEFAULT - флаг "Выбирать по умолчанию"; "Y" - да, "N" - нет  Необязательный параметр. |
| **is\_filtered** | Переменная возвращающая true в том случае если список результатов отфильтрован по какому либо критерию; либо false в противном случае. С версии 12.0.0 изменен на **isFiltered**. |

#### Возвращаемое значение

Возвращается объект CDBResult.

### Примеры использования

```
<?
$FilterArr = Array(
	"find_id",
	"find_lid",
	"find_type",
	"find_name",
	"find_sid",
	"find_responsible",
	"find_responsible_id",
	"find_default"
);
if (strlen($set_filter)>0) InitFilterEx($FilterArr,"TICKET_DICTIONARY_LIST","set"); else InitFilterEx($FilterArr,"TICKET_DICTIONARY_LIST","get");
if (strlen($del_filter)>0) DelFilterEx($FilterArr,"TICKET_DICTIONARY_LIST");
$arFilter = Array(
	"ID"				=> $find_id,
	"LID"				=> $find_lid,
	"TYPE"				=> $find_type,
	"NAME"				=> $find_name,
	"SID"				=> $find_sid,
	"RESPONSIBLE_ID"	=> $find_responsible_id,
	"RESPONSIBLE"		=> $find_responsible,
	"DEFAULT"			=> $find_default
);
$tdic = CTicketDictionary::GetList($by, $order, $arFilter, $is_filtered);
?>Копировать
```

```
//получим список статусов для текущего сайта $arFilter = Array(
	"LID" => SITE_ID,
	"TYPE" => "S",
);
//сортировка задется через переменные
$by = "s_c_sort";
$sort = "asc";
//отбор и вывод
$rsStatus = CTicketDictionary::GetList($by, $sort, $arFilter, $is_filtered); while($arRes = $rsStatus->GetNext()) 
{
	echo $arRes["NAME"], "";
}Копировать
```

Новинки документации в соцсетях:
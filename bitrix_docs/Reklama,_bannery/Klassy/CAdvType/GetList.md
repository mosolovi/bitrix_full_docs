[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvType](/api_help/advertising/classes/cadvtype/index.php)

GetList (3.3.4)

GetList
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
record set
CAdvType::GetList(
	varchar &by,
	varchar &order,
	array arFilter=array(),
	boolean &is_filtered,
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод предназначен для получения списка типов баннеров. Метод нестатический.

#### Параметры метода

| Параметры | Описание | С версии |
| --- | --- | --- |
| by | Идентификатор, позволяющий задать имя поля для сортировки. Допустимы следующие значения:  * s\_sid - по символьному ID типа * s\_date\_modify - по дате модификации * s\_modified\_by - по ID пользователя, изменившего тип * s\_date\_create - по дате создания * s\_created\_by - по ID пользователя, создавшего тип * s\_active - по флагу активности * s\_name - по имени * s\_banners - по количеству баннеров данного типа * s\_description - по описанию |  |
| order | Порядок сортировки. Допустимы следующие значения:  * desc - по убыванию (значение по умолчанию) * asc - по возрастанию |  |
| arFilter | Массив для фильтрации значений. Необязательный параметр. В массиве допустимы следующие индексы:  * SID - символьный ID типа (допускается сложная логика) * SID\_EXACT\_MATCH - "Y" - при фильтрации по символьному ID типа будет искаться точное совпадение (по умолчанию); "N" - в противном случае будет искаться вхождение * DATE\_MODIFY\_1 - левая часть интервала для даты модификации типа * DATE\_MODIFY\_2 - правая часть интервала для даты модификации типа * ACTIVE - флаг активности типа ("Y" - активен; "N" - не активен) * NAME - имя типа (допускается сложная логика) * NAME\_EXACT\_MATCH - "Y" - при фильтрации по имени типа будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) * DESCRIPTION - описание типа (допускается сложная логика) * DESCRIPTION\_EXACT\_MATCH - "Y" - при фильтрации по описанию типа будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) |  |
| is\_filtered | Переменная, возвращающая true в том случае, если список типов отфильтрован по какому либо критерию; либо false в противном случае. |  |
| CHECK\_RIGHTS | Параметр проверяет уровень доступа к модулю Реклама (администратор рекламы, рекламодатель и т.д.) Если параметр определён как "N", то считается, что текущий пользователь обладает административными правами доступа к модулю Реклама. Если параметр пропущен либо равен "Y", то метод проверяет уровень доступа к контракту, которому принадлежит баннер. Необязательный параметр. | 3.3.14 |

### Примеры использования

```
<?
$FilterArr = Array(
	"find_sid",
	"find_sid_exact_match",
	"find_date_modify_1", 
	"find_date_modify_2", 
	"find_active", 
	"find_name",
	"find_name_exact_match",
	"find_description", 
	"find_description_exact_match"
);
if (strlen($set_filter)>0) InitFilterEx($FilterArr,"ADV_TYPE_LIST","set"); 
else InitFilterEx($FilterArr,"ADV_TYPE_LIST","get");
if (strlen($del_filter)>0) DelFilterEx($FilterArr,"ADV_TYPE_LIST");
InitBVar($find_sid_exact_match);
InitBVar($find_name_exact_match);
InitBVar($find_description_exact_match);
$arFilter = Array(
	"SID"					   => $find_sid,
	"SID_EXACT_MATCH"		   => $find_sid_exact_match,
	"DATE_MODIFY_1"			 => $find_date_modify_1, 
	"DATE_MODIFY_2"			 => $find_date_modify_2, 
	"ACTIVE"					=> $find_active, 
	"NAME"					  => $find_name,
	"NAME_EXACT_MATCH"		  => $find_name_exact_match,
	"DESCRIPTION"			   => $find_description,
	"DESCRIPTION_EXACT_MATCH"   => $find_description_exact_match,
);
$rsAdvType = CAdvType::GetList($by, $order, $arFilter, $is_filtered, "Y");
?>Копировать
```

#### Пример массива, получаемого после Fetch одной строки выборки данного метода

```
<?
Array
(
	[SID] => TOP
	[ACTIVE] => Y
	[SORT] => 10
	[NAME] => Top banner
	[DESCRIPTION] => описание типа
	[DATE_CREATE] => 03.06.2004 17:27:00
	[DATE_MODIFY] => 03.06.2004 17:27:00
	[CREATED_BY] => 2
	[MODIFIED_BY] => 2
	[BANNER_COUNT] => 63
)
?>Копировать
```

Новинки документации в соцсетях:
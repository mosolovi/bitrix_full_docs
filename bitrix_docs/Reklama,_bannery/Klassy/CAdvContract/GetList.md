[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvContract](/api_help/advertising/classes/cadvcontract/index.php)

GetList (3.3.4)

GetList
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
record set
CAdvContract::GetList(
	varchar &by,
	varchar &order,
	array arFilter=array(),
	boolean &is_filtered,
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод предназначен для получения списка контрактов. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| by | Идентификатор, позволяющий задать имя поля для сортировки. Допустимы следующие значения:  * s\_id - по ID * s\_lamp - по индикатору контракта * s\_name - по заголовку контракта * s\_description - по описанию контракта * s\_active - по флагу активности * s\_weight - по весу * s\_sort - по сортировке * s\_date\_modify - по дате модификации * s\_modified\_by - по ID пользователя, изменившего контракт * s\_banner\_count - по числу баннеров, приписанных к контракту * s\_ctr - по отклику (CTR) контракта * s\_show\_count - по суммарному числу показов баннеров контракта * s\_max\_show\_count - по максимальному суммарному числу всех показов баннеров контракта * s\_click\_count - по суммарному числу кликов на баннеры контракта * s\_max\_click\_count - по максимальному суммарному числу кликов на баннеры контракта |
| arFilter | Массив для фильтрации значений. Необязательный параметр. В массиве допустимы следующие индексы:  * ID - ID контракта (допускается сложная логика) * - "Y" - при фильтрации по ID контракта будет искаться точное совпадение (по умолчанию); "N" - в противном случае будет искаться вхождение * LAMP - значение индикатора: "red", "green" * DATE\_MODIFY\_1 - левая часть интервала для даты модификации контракта * DATE\_MODIFY\_2 - правая часть интервала для даты модификации контракта * NAME - имя контракта (допускается сложная логика) * NAME\_EXACT\_MATCH - "Y" - при фильтрации по имени контракта будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) * DESCRIPTION - описание контракта (допускается сложная логика) * DESCRIPTION\_EXACT\_MATCH - "Y" - при фильтрации по описанию контракта будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) * OWNER - ID, ФИО, логин владельца контракта (допускается сложная логика) * OWNER\_EXACT\_MATCH - "Y" - при фильтрации по ID, ФИО, логину владельца контракта будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) * BANNER\_COUNT\_1 - левая часть интервала для числа баннеров контракта * BANNER\_COUNT\_2 - правая часть интервала для числа баннеров контракта * SHOW\_COUNT\_1 - левая часть интервала для суммарного числа показов баннеров контракта * SHOW\_COUNT\_2 - правая часть интервала для суммарного числа показов баннеров контракта * CLICK\_COUNT\_1 - левая часть интервала для суммарного числа кликов по баннерам контракта * CLICK\_COUNT\_2 - правая часть интервала для суммарного числа кликов по баннерам контракта * CTR\_1 - левая часть интервала для CTR контракта * CTR\_2 - правая часть интервала для CTR контракта * ADMIN\_COMMENTS - административный комментарий к контракту (допускается сложная логика) * ADMIN\_COMMENTS\_EXACT\_MATCH - "Y" - при фильтрации по административному комментарию к контракту будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) |
| CHECK\_RIGHTS | Параметр проверяет уровень доступа к модулю Реклама (администратор рекламы, рекламодатель и т.д.) Если параметр определён как "N", то считается, что текущий пользователь обладает административными правами доступа к модулю Реклама. Если параметр пропущен либо равен "Y", то метод проверяет уровень доступа к контракту, которому принадлежит баннер. Необязательный параметр. |

### Примеры использования

```
<?
// фильтр
$FilterArr = Array(
	"find_id",
	"find_id_exact_match",
	"find_date_modify_1", 
	"find_date_modify_2", 
	"find_name",
	"find_name_exact_match",
	"find_description", 
	"find_description_exact_match",
	"find_lamp", 
	"find_owner",
	"find_owner_exact_match",
	"find_banner_count_1",
	"find_banner_count_2",
	"find_show_count_1",
	"find_show_count_2",
	"find_click_count_1",
	"find_click_count_2",
	"find_ctr_1",
	"find_ctr_2",
	"find_admin_comments",
	"find_admin_comments_exact_match"
);
if (strlen($set_filter)>0) InitFilterEx($FilterArr,"ADV_CONTRACT_LIST","set"); 
else InitFilterEx($FilterArr,"ADV_CONTRACT_LIST","get");
if (strlen($del_filter)>0) DelFilterEx($FilterArr,"ADV_CONTRACT_LIST");
InitBVar($find_id_exact_match);
InitBVar($find_name_exact_match);
InitBVar($find_description_exact_match);
InitBVar($find_owner_exact_match);
InitBVar($find_admin_comments_exact_match);
$arFilter = Array(
	"ID"							=> $find_id,
	"ID_EXACT_MATCH"				=> $find_id_exact_match,
	"DATE_MODIFY_1"				 => $find_date_modify_1, 
	"DATE_MODIFY_2"				 => $find_date_modify_2, 
	"NAME"						  => $find_name,
	"NAME_EXACT_MATCH"			  => $find_name_exact_match,
	"DESCRIPTION"				   => $find_description,
	"DESCRIPTION_EXACT_MATCH"	   => $find_description_exact_match,
	"LAMP"						  => $find_lamp,
	"OWNER"						 => $find_owner,
	"OWNER_EXACT_MATCH"			 => $find_owner_exact_match,
	"BANNER_COUNT_1"				=> $find_banner_count_1,
	"BANNER_COUNT_2"				=> $find_banner_count_2,
	"SHOW_COUNT_1"				  => $find_show_count_1,
	"SHOW_COUNT_2"				  => $find_show_count_2,
	"CLICK_COUNT_1"				 => $find_click_count_1,
	"CLICK_COUNT_2"				 => $find_click_count_2,
	"CTR_1"						 => $find_ctr_1,
	"CTR_2"						 => $find_ctr_2,
	"ADMIN_COMMENTS"				=> $find_admin_comments,
	"ADMIN_COMMENTS_EXACT_MATCH"	=> $find_admin_comments_exact_match
);
$rsAdvContract = CAdvContract::GetList($by, $order, $arFilter, $is_filtered, "N");
?>Копировать
```

#### Пример массива, получаемого после Fetch одной строки выборки данного метода

```
<?
Array
(
	[LAMP] => green
	[ID] => 3
	[ACTIVE] => Y
	[NAME] => заголовок контракта
	[DESCRIPTION] => описание контракта
	[ADMIN_COMMENTS] => административный комментарий
	[WEIGHT] => 1000
	[SORT] => 200
	[MAX_SHOW_COUNT] => 1000
	[SHOW_COUNT] => 312
	[MAX_CLICK_COUNT] => 100
	[CLICK_COUNT] => 64
	[EMAIL_COUNT] => 0
	[CREATED_BY] => 2
	[MODIFIED_BY] => 2
	[DEFAULT_STATUS_SID] => READY
	[CTR] => 20.51
	[DATE_SHOW_FROM] => 15.06.2004
	[DATE_SHOW_TO] => 07.07.2009
	[DATE_CREATE] => 07.06.2004 19:04:55
	[DATE_MODIFY] => 24.06.2004 10:56:08
	[BANNER_COUNT] => 12
)
?>Копировать
```

Новинки документации в соцсетях:
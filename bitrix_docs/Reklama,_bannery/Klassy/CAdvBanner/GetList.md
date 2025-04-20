[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvBanner](/api_help/advertising/classes/cadvbanner/index.php)

GetList (3.3.4)

GetList
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
record set
CAdvBanner::GetList(
	varchar &by,
	varchar &order,
	array arFilter=array(),
	boolean &is_filtered,
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод предназначен для получения списка баннеров. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| by | Идентификатор, позволяющий задать имя поля для сортировки. Допустимы следующие значения:  * s\_id - по ID * s\_lamp - по индикатору * s\_name - по имени баннера * s\_type\_sid - по типу баннера * s\_contract\_id - по ID контракта * s\_group\_sid - по имени группы * s\_show\_count - по количеству показов * s\_max\_show\_count - по максимальному количеству показов * s\_date\_last\_show - по дате последнего показа * s\_click\_count - по количеству кликов на баннер * s\_max\_click\_count - по максимальному количеству кликов * s\_date\_last\_click - по дате последнего клика * s\_active - по флагу активности * s\_weight - по весу баннера * s\_status\_sid - по статусу баннера * s\_date\_show\_from - по дате начала показов * s\_date\_show\_to - по дате окончания показов * s\_ctr - по CTR баннера |
| order | Порядок сортировки. Допустимы следующие значения:  * desc - по убыванию (значение по умолчанию) * asc - по возрастанию |
| arFilter | Массив для фильтрации значений. Необязательный параметр. В массиве допустимы следующие индексы:  * \* ID - ID баннера * ID\_EXACT\_MATCH - "Y" - при фильтрации по ID баннера будет искаться точное совпадение (по умолчанию); "N" - в противном случае будет искаться вхождение * ACTIVE - активность, значения Y/N * LAMP - значение индикатора: "red", "green" * LANG - двухсимвольный идентификатор языковой части сайта в которой будет показываться баннер * SHOW\_COUNT\_1 - левая часть интервала для числа показов * SHOW\_COUNT\_2 - правая часть интервала для числа показов * CLICK\_COUNT\_1 - левая часть интервала для числа кликов * CLICK\_COUNT\_2 - правая часть интервала для числа кликов * CTR\_1 - левая часть интервала для CTR баннера * CTR\_2 - правая часть интервала для CTR баннера * \* GROUP - имя группы баннера * GROUP\_EXACT\_MATCH - "Y" - при фильтрации по имени группы будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) * \* STATUS\_SID - символьный код статуса; символьный код статуса может принимать следующие значения:   + PUBLISHED - баннер подтвержден и опубликован   + READY - баннер на рассмотрении   + REJECTED - баннер отклонен * \* CONTRACT\_ID - ID контракта * CONTRACT\_ID\_EXACT\_MATCH - "Y" - при фильтрации по ID контракта будет искаться точное совпадение (по умолчанию); "N" - в противном случае будет искаться вхождение * \* CONTRACT - ID, имя, описание контракта * CONTRACT\_EXACT\_MATCH - "Y" - при фильтрации по ID, имени, описанию контракта будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) * \* TYPE\_SID - символьный код типа баннера * TYPE\_SID\_EXACT\_MATCH - "Y" - при фильтрации по символьному коду типа баннера будет искаться точное совпадение (по умолчанию); "N" - в противном случае будет искаться вхождение * \* NAME - имя баннера * NAME\_EXACT\_MATCH - "Y" - при фильтрации по имени баннера будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) * \* CODE - код баннера * CODE\_EXACT\_MATCH - "Y" - при фильтрации по коду баннера будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) * \* COMMENTS - комментарий к баннеру * COMMENTS\_EXACT\_MATCH - "Y" - при фильтрации по комментарию к баннеру будет искаться точное совпадение; "N" - в противном случае будет искаться вхождение (по умолчанию) * SITE - для фильтрации по сайтам. |
| is\_filtered | Переменная, возвращающая true в том случае, если список баннеров отфильтрован по какому-либо критерию; либо false в противном случае. |
| CHECK\_RIGHTS | Параметр проверяет уровень доступа к модулю Реклама (администратор рекламы, рекламодатель и т.д.). Если параметр определён как "N", то считается, что текущий пользователь обладает административными правами доступа к модулю Реклама. Если параметр пропущен либо равен "Y", то функция проверяет уровень доступа к модулю. Необязательный параметр. |

**\*** - допускается [сложная логика](/api_help/main/general/filter.php) и использование
логических операторов



Облегчайте поиск информации вместе с логическими операторами. Система допускает использование пяти видов логических операторов. Давайте их рассмотрим.  
  
[Подробнее ...](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=35&LESSON_ID=2057) в курсе **Администратор.Базовый**.

### Примеры использования

```
<?
$FilterArr = Array(
	"find_id",
	"find_id_exact_match",
	"find_lamp",
	"find_lang",
	"find_show_count_1",
	"find_show_count_2",
	"find_click_count_1",
	"find_click_count_2",
	"find_ctr_1",
	"find_ctr_2",
	"find_contract_id",
	"find_contract",
	"find_contract_exact_match",
	"find_group",
	"find_group_exact_match",
	"find_status_sid",
	"find_type_sid",
	"find_type",
	"find_type_exact_match",
	"find_name",
	"find_name_exact_match",
	"find_code",
	"find_code_exact_match",
	"find_comments",
	"find_comments_exact_match"
	);
if (strlen($set_filter)>0) InitFilterEx($FilterArr,"ADV_BANNER_LIST","set"); 
else InitFilterEx($FilterArr,"ADV_BANNER_LIST","get");
if (strlen($del_filter)>0) DelFilterEx($FilterArr,"ADV_BANNER_LIST");
InitBVar($find_id_exact_match);
InitBVar($find_status_exact_match);
InitBVar($find_group_exact_match);
InitBVar($find_contract_exact_match);
InitBVar($find_type_exact_match);
InitBVar($find_name_exact_match);
InitBVar($find_code_exact_match);
InitBVar($find_comments_exact_match);
$arFilter = Array(
	"ID"					=> $find_id,
	"ID_EXACT_MATCH"		=> $find_id_exact_match,
	"LAMP"				  => $find_lamp,
	"LANG"				  => $find_lang,
	"SHOW_COUNT_1"		  => $find_show_count_1,
	"SHOW_COUNT_2"		  => $find_show_count_2,
	"CLICK_COUNT_1"		 => $find_click_count_1,
	"CLICK_COUNT_2"		 => $find_click_count_2,
	"CTR_1"				 => $find_ctr_1,
	"CTR_2"				 => $find_ctr_2,
	"GROUP"				 => $find_group,
	"GROUP_EXACT_MATCH"	 => $find_group_exact_match,
	"STATUS_SID"			=> $find_status_sid,
	"CONTRACT_ID"		   => $find_contract_id,
	"CONTRACT"			  => $find_contract,
	"CONTRACT_EXACT_MATCH"  => $find_contract_exact_match,
	"TYPE_SID"			  => $find_type_sid,
	"TYPE"				  => $find_type,
	"TYPE_EXACT_MATCH"	  => $find_type_exact_match,
	"NAME"				  => $find_name,
	"NAME_EXACT_MATCH"	  => $find_name_exact_match,
	"CODE"				  => $find_code,
	"CODE_EXACT_MATCH"	  => $find_code_exact_match,
	"COMMENTS"			  => $find_comments,
	"COMMENTS_EXACT_MATCH"  => $find_comments_exact_match
	);
$rsBanners = CAdvBanner::GetList($by, $order, $arFilter, $is_filtered, "N");
$rsBanners->NavStart(20);
$rsBanners->NavPrint("Баннеры");
while($arBanner = $rsBanners->NavNext(true, "f_"))
{
	echo "<pre>"; print_r($arBanner); echo "</pre>";
}
?>
Копировать
```

#### Пример массива, получаемого после Fetch одной строки выборки данного метода

```
<?
Array
(
	[LAMP] => green
	[ID] => 88
	[CONTRACT_ID] => 1
	[TYPE_SID] => TOP
	[GROUP_SID] => 
	[STATUS_SID] => PUBLISHED
	[STATUS_COMMENTS] =>
	[NAME] =>
	[ACTIVE] => Y
	[LID] => 
	[WEIGHT] => 100
	[MAX_SHOW_COUNT] => 300
	[MAX_CLICK_COUNT] => 100
	[SHOW_COUNT] => 102
	[CLICK_COUNT] => 4
	[IMAGE_ID] => 1032
	[IMAGE_ALT] =>
	[URL] => http://www.1c-bitrix.ru?banner_param=<code>#EVENT_GID#</code>
	[URL_TARGET] => _parent
	[CODE] => <TABLE class=smalltext cellSpacing=0 cellPadding=0 width=145>
<TR>
<TD></TD>
<TD>
<DIV align=center>
<A class=righthead href="/ru/partners/partnership.php">Партнёрская программа</A>
</DIV>
</TD></TR>
<TR>
<TD></TD>
<TD height=8></TD></TR>
<TR>
<TD width=5></TD>
<TD vAlign=bottom>
<DIV align=center>
<A href="/ru/partners/partnership.php">
<IMG height=95 src="/images/advert/free.gif" width=100 border=0></A>
</DIV></TD></TR>
<TR>
<TD></TD>
<TD height=5></TD></TR>
<TR>
<TD></TD>
<TD>Разработчики сайтов и интеграторы получают:<BR>
<B><FONT class=smalltext>
<IMG height=8 src="/images/list_bullet.gif" width=8>
</FONT></B> 
<FONT color=#ff5a31>скидки до 50%</FONT> <BR>
<B><FONT class=smalltext>
<IMG height=8 src="/images/list_bullet.gif" width=8>
</FONT></B> 
<FONT color=#ff5a31>бесплатную копиию</FONT>
</TD></TR>
<TR>
<TD></TD>
<TD height=5></TD></TR>
<TR>
<TD></TD>
<TD>
<DIV align=right>
<A class=bottomlinks href="/ru/partners/partnership.php">Подробнее</A>
<IMG height=7 src="/images/main_button_more_3.gif" width=7>
</DIV></TD></TR></TABLE>
	[CODE_TYPE] => html
	[STAT_EVENT_1] => 
	[STAT_EVENT_2] => 
	[STAT_EVENT_3] => 
	[FOR_NEW_GUEST] => 
	[COMMENTS] => 
	[CREATED_BY] => 2
	[MODIFIED_BY] => 2
	[CTR] => 3.92
	[DATE_LAST_SHOW] => 24.06.2004 17:39:50
	[DATE_LAST_CLICK] => 24.06.2004 14:47:53
	[DATE_SHOW_FROM] => 10.06.2004
	[DATE_SHOW_TO] => 07.07.2007
	[DATE_CREATE] => 10.06.2004 11:25:59
	[DATE_MODIFY] => 24.06.2004 14:33:56
	[CONTRACT_NAME] => Default
	[TYPE_NAME] => Top banner
)
?>
Копировать
```

Новинки документации в соцсетях:
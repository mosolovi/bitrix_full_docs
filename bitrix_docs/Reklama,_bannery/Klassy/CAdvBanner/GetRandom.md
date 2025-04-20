[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvBanner](/api_help/advertising/classes/cadvbanner/index.php)

GetRandom (3.3.4)

GetRandom
=========

Включить вкладки

Описание и параметры

Пример

### Описание и параметры

```
array
CAdvBanner::GetRandom(
	varchar(255) TYPE_SID
);Копировать
```

Метод выбирает в соответствии с весами (приоритетами) произвольный баннер по указанному типу и возвращает массив, частично его описывающий. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| TYPE\_SID | Символьный идентификатор типа. |

### Пример

#### Пример массива, возвращаемого методом

```
Array
(
	[ID] => 94
	[CONTRACT_ID] => 3
	[TYPE_SID] => LEFT2
	[STATUS_SID] => PUBLISHED
	[STATUS_COMMENTS] => 
	[NAME] => Баннер
	[GROUP_SID] => группа 1
	[ACTIVE] => Y
	[LID] => 
	[WEIGHT] => 2000
	[MAX_SHOW_COUNT] => 1000
	[MAX_CLICK_COUNT] => 50
	[SHOW_COUNT] => 67
	[CLICK_COUNT] => 4
	[DATE_LAST_SHOW] => 2004-06-24 14:47:47
	[DATE_LAST_CLICK] => 2004-06-22 11:33:18
	[DATE_SHOW_FROM] => 2004-01-07 00:00:00
	[DATE_SHOW_TO] => 2004-07-07 23:59:59
	[IMAGE_ID] => 1028
	[IMAGE_ALT] => текст подсказки
	[URL] => http://www.1c-bitrix.ru
	[URL_TARGET] => _parent
	[CODE] => <TABLE class=smalltext cellSpacing=0 cellPadding=0 width=145>
<TR>
<TD></TD>
<TD>
<DIV align=center>
<A class=righthead href="/ru/partners/partnership.php">Партнёрская программа</A>
</DIV></TD></TR>
<TR>
<TD></TD>
<TD height=8></TD></TR>
<TR>
<TD width=5></TD>
<TD vAlign=bottom>
<DIV align=center><A href="/ru/partners/partnership.php">
<IMG height=95 src="/images/advert/free.gif" width=100 border=0>
</A></DIV></TD></TR>
<TR>
<TD></TD>
<TD height=5></TD></TR>
<TR>
<TD></TD>
<TD>Разработчики сайтов и интеграторы получают:<BR><B>
<FONT class=smalltext><IMG height=8 src="/images/list_bullet.gif" width=8></FONT></B> 
<FONT color=#ff5a31>скидки до 50%</FONT> <BR><B>
<FONT class=smalltext><IMG height=8 src="/images/list_bullet.gif" width=8></FONT></B> 
<FONT color=#ff5a31>бесплатную копиию</FONT></TD></TR>
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
	[DATE_CREATE] => 2004-06-15 15:13:41
	[CREATED_BY] => 342
	[DATE_MODIFY] => 2004-06-22 19:31:50
	[MODIFIED_BY] => 343
)
Копировать
```

Новинки документации в соцсетях:
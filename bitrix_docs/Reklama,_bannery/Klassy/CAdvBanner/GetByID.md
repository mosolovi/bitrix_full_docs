[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvBanner](/api_help/advertising/classes/cadvbanner/index.php)

GetByID (3.3.4)

GetByID
=======

Включить вкладки

Описание и параметры

Пример

### Описание и параметры

```
record set
CAdvBanner::GetByID(
	int BANNER_ID,
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод возвращает баннер по его ID. Метод нестатический.

#### Параметры метода

| Параметры | Описание | С версии |
| --- | --- | --- |
| BANNER\_ID | ID баннера. |  |
| CHECK\_RIGHTS | Параметр проверяет уровень доступа к модулю Реклама (администратор рекламы, рекламодатель и т.д.). Если параметр определён как "N", то считается, что текущий пользователь обладает административными правами доступа к модулю Реклама. Если параметр пропущен либо равен "Y", то метод проверяет уровень доступа к контракту, которому принадлежит баннер. Необязательный параметр. | 3.3.14 |

### Пример

#### Пример массива, получаемого после Fetch результата, возвращенного данным методом

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
	[URL] => http://www.1c-bitrix.ru?banner_param=#EVENT_GID#
	[URL_TARGET] => _parent
	[CODE] =>
<TABLE class=smalltext cellSpacing=0 cellPadding=0 width=145>
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
<DIV align=center>
<A href="/ru/partners/partnership.php">
<IMG height=95 src="/images/advert/free.gif" width=100 border=0></A></DIV></TD></TR>
<TR>
<TD></TD>
<TD height=5></TD></TR>
<TR>
<TD></TD>
<TD>Разработчики сайтов и интеграторы получают:<BR>
<B><FONT class=smalltext>
<IMG height=8 src="/images/list_bullet.gif" width=8>
</FONT></B> 
<FONT color=#ff5a31>скидки до 50%</FONT> 
<BR><B><FONT class=smalltext>
<IMG height=8 src="/images/list_bullet.gif" width=8>
</FONT></B> 
<FONT color=#ff5a31>бесплатную копиию</FONT></TD></TR>
<TR>
<TD></TD>
<TD height=5></TD></TR>
<TR>
<TD></TD>
<TD>
<DIV align=right>
<A class=bottomlinks
href="/ru/partners/partnership.php">Подробнее</A>
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
?>Копировать
```

Новинки документации в соцсетях:
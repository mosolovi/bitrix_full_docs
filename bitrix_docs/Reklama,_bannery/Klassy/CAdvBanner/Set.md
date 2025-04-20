[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvBanner](/api_help/advertising/classes/cadvbanner/index.php)

Set (3.3.4)

Set
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CAdvBanner::Set(
	array arFields,
	int BANNER_ID="",
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод создает новый баннер, либо модифицирует существующий в случае указания во втором параметре ID баннера. Возвращает ID созданного баннера, либо ID модифицированного баннера. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| arFields | Массив параметров баннера. В массиве допустимы следующие индексы:  * CONTRACT\_ID - ID контракта (обязательный параметр для нового баннера) * TYPE\_SID - символьный идентификатор типа баннера (обязательный параметр для нового баннера) * STATUS\_SID - символьный идентификатор статуса баннера, допустимы следующие значения:   + PUBLISHED - баннер подтвержден и опубликован   + READY - баннер на рассмотрении   + REJECTED - баннер отклонен * STATUS\_COMMENTS - комментарий к статусу * NAME - имя баннера * GROUP\_SID - имя группы баннера * ACTIVE - флаг активности: "Y" - баннер активен; "N" - баннер не активен; * arrSITE - код языковой части сайта, в которой будет показываться баннер * WEIGHT - вес (приоритет) баннера * MAX\_SHOW\_COUNT - максимальное количество показов баннера * RESET\_SHOW\_COUNT - флаг необходимости сбросить счетчик показов у баннера (автоматически будет уменьшен счетчик показов у всего контракта) * MAX\_CLICK\_COUNT - максимальное количество кликов на баннер * RESET\_CLICK\_COUNT - флаг необходимости сбросить счетчик кликов на баннер (автоматически будет уменьшен счетчик кликов у всего контракта) * DATE\_SHOW\_FROM - дата начала показов баннера * DATE\_SHOW\_TO - дата окончания показов баннера * arrIMAGE\_ID - массив, описывающий загружаемое изображение; в массиве допустимые следующие индексы:   + name - исходное имя загружаемого файла   + type - тип загружаемого файла (например: "image/gif")   + tmp\_name - имя временного файла на сервере   + error - код ошибки ("0" - нет ошибок)   + size - размер загружаемого файла   + MODULE\_ID - идентификатор модуля ("advertising") * IMAGE\_ALT - текст всплывающей подсказки к изображению * URL - ссылка на изображение. В данном поле можно использовать шаблон `#EVENT_GID#`, который при клике на баннер будет заменен на идентификатор посетителя, который используется в модуле статистики при загрузке событий. * URL\_TARGET - в данном поле вы можете задать строку, влияющую на поведение браузера при нажатии на ссылку-изображение:   + \_self - открыть в текущем окне   + \_blank - открыть в новом окне   + \_parent - открыть в своем фреймсете   + \_top - во всем текущем окне браузера * CODE - код баннера * CODE\_TYPE - тип кода баннера: "text" - код баннера будет выведен как текст; "html" - код баннера будет выведен как HTML; * STAT\_EVENT\_1 - идентификатор типа события - " `event1`" (события регистрируются в модуле статистики) * STAT\_EVENT\_2 - идентификатор типа события - " `event2`" * STAT\_EVENT\_3 - дополнительный параметр события - " `event3`". В коде баннера, `event1`, `event2`, `event3` можно использовать следующие шаблоны:   + `#BANNER_NAME#` - имя баннера   + `#BANNER_ID#` - ID баннера   + `#CONTRACT_ID#` - ID контракта   + `#TYPE_SID#` - тип баннера * FOR\_NEW\_GUEST - "Y" - показывать баннер только для новых посетителей; "N" - показывать баннер только для посетителей уже посещавших сайт * COMMENTS - комментарий к баннеру * arrSHOW\_PAGE - массив страниц и разделов сайта, на которых должен показываться баннер * arrNOT\_SHOW\_PAGE - массив страниц и разделов сайта, на которых не должен показываться баннер * arrCOUNTRY - массив двухсимвольных кодов стран, посетителям которых необходимо показывать баннер * arrSTAT\_ADV - массив идентификаторов рекламных кампаний, посетителям которых необходимо показывать баннер (как на прямых заходах, так и на возвратах) * arrWEEKDAY - массив, описывающий время и дни недели для показа баннера; в массиве допустимы следующие индексы:   + SUNDAY - массив часов в которые надо показывать баннер в воскресенье (0-23)   + MONDAY - -||- в понедельник   + TUESDAY - -||- во вторник   + WEDNESDAY - -||- в среду   + THURSDAY - -||- в четверг   + FRIDAY - -||- в пятницу   + SATURDAY - -||- в субботу * SEND\_EMAIL - флаг необходимости отослать EMail владельцам контракта при смене статуса баннера; письмо отсылается по шаблону "Изменился статус баннера" |
| BANNER\_ID | ID баннера, если не указывать - создаётся новый баннер. |
| CHECK\_RIGHTS | Флаг необходимости проверки прав текущего пользователя: "Y" - необходимо проверить права текущего пользователя; "N" - баннер создавать и модифицировать независимо от прав текущего пользователя. Необязательный параметр. |

### Примеры использования

Пример кода, добавляющего новый баннер, либо модифицирующего существующий:

```
<?
if ((strlen($save)>0 || strlen($apply)>0) && $REQUEST_METHOD=="POST")
{
	InitBVar($SEND_EMAIL);
	$arrIMAGE_ID = $HTTP_POST_FILES["IMAGE_ID"];
	$arrIMAGE_ID["MODULE_ID"] = "advertising";
	$arrIMAGE_ID["del"] = ${"IMAGE_ID_del"};
	$arrWEEKDAY = array(
		"SUNDAY"	=> $arrSUNDAY,
		"MONDAY"	=> $arrMONDAY,
		"TUESDAY"   => $arrTUESDAY,
		"WEDNESDAY" => $arrWEDNESDAY,
		"THURSDAY"  => $arrTHURSDAY,
		"FRIDAY"	=> $arrFRIDAY,
		"SATURDAY"  => $arrSATURDAY
	);
	if ($action=="view" && $isAbsAdmin)
	{
		 $arFields = array(
			"STATUS_SID"		=> $STATUS_SID,
			"STATUS_COMMENTS"   => $STATUS_COMMENTS
		);
	}
	else
	{
		 $arFields = array(
			"CONTRACT_ID"	   => $CONTRACT_ID,
			"TYPE_SID"		  => $TYPE_SID,
			"STATUS_SID"		=> $STATUS_SID,
			"STATUS_COMMENTS"   => $STATUS_COMMENTS,
			"NAME"			  => $NAME,
			"GROUP_SID"		 => $GROUP_SID,
			"ACTIVE"		=> $ACTIVE,
			"arrSITE"		=> $arrSITE,
			"WEIGHT"		=> $WEIGHT,
			"MAX_SHOW_COUNT"	=> $MAX_SHOW_COUNT,
			"RESET_SHOW_COUNT"  => $RESET_SHOW_COUNT,
			"MAX_CLICK_COUNT"   => $MAX_CLICK_COUNT,
			"RESET_CLICK_COUNT" => $RESET_CLICK_COUNT,
			"DATE_SHOW_FROM"	=> $DATE_SHOW_FROM,
			"DATE_SHOW_TO"	  => $DATE_SHOW_TO,
			"arrIMAGE_ID"	   => $arrIMAGE_ID,
			"IMAGE_ALT"		 => $IMAGE_ALT,
			"URL"			   => $URL,
			"URL_TARGET"		=> $URL_TARGET,
			"CODE"			  => $CODE,
			"CODE_TYPE"		 => $CODE_TYPE,
			"STAT_EVENT_1"	  => $STAT_EVENT_1,
			"STAT_EVENT_2"	  => $STAT_EVENT_2,
			"STAT_EVENT_3"	  => $STAT_EVENT_3,
			"FOR_NEW_GUEST"	 => $FOR_NEW_GUEST,
			"COMMENTS"		  => $COMMENTS,
			"arrSHOW_PAGE"	  => split("[\n\r]",$SHOW_PAGE),
			"arrNOT_SHOW_PAGE"  => split("[\n\r]",$NOT_SHOW_PAGE),
			"arrCOUNTRY"		=> $arrCOUNTRY,
			"arrSTAT_ADV"	   => $arrSTAT_ADV,
			"arrWEEKDAY"		=> $arrWEEKDAY,
			"SEND_EMAIL"		=> $SEND_EMAIL
		);
	}
	if ($ID = CAdvBanner::Set($arFields, $ID))
	{
		if (strlen($strError) <= 0)
		{
			 if (strlen($save) > 0)
				 LocalRedirect("adv_banner_list.php?lang=".LANG);
			 else
				 LocalRedirect("adv_banner_edit.php?ID=".$ID."&CONTRACT_ID=".$CONTRACT_ID."&lang=".LANG."&action=".$action);
		}
	}
	$DB->PrepareFields("b_adv_banner");
}
?>
Копировать
```

Новинки документации в соцсетях:
[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvContract](/api_help/advertising/classes/cadvcontract/index.php)

Set (3.3.4)

Set
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CAdvContract::Set(
	array arFields,
	int CONTRACT_ID="",
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод создает новый контракт, либо модифицирует существующий в случае указания во втором параметре ID контракта. Возвращает ID созданного контракта, либо ID модифицированного контракта. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| arFields | Массив параметров контракта. В массиве допустимы следующие индексы:  * ACTIVE - флаг активности: "Y" - контракт активен; "N" - контракт не активен; * NAME - заголовок контракта * DESCRIPTION - описание контракта * ADMIN\_COMMENTS - административный комментарий * WEIGHT - вес (приоритет) контракта * SORT - порядок сортировки * MAX\_SHOW\_COUNT - максимальное суммарное число показов всех баннеров контракта * MAX\_CLICK\_COUNT - максимальное суммарное число кликов на все баннеры контракта * DATE\_SHOW\_FROM - дата начала показов баннеров * DATE\_SHOW\_TO - дата окончания показов баннеров * DEFAULT\_STATUS\_SID - статус по умолчанию для новых баннеров или при модификации отображаемой части существующих, допустимы следующие значения:   + PUBLISHED - баннер подтвержден и опубликован   + READY - баннер на рассмотрении   + REJECTED - баннер отклонен * arrSHOW\_PAGE - массив страниц и разделов сайта, на которых должны показываться баннеры контракта * arrNOT\_SHOW\_PAGE - массив страниц и разделов сайта, на которых не могут показываться баннеры контракта * arrTYPE - массив доступных типов баннеров * arrWEEKDAY - массив, описывающий время и дни недели для показа баннера; в массиве допустимы следующие индексы:   + SUNDAY - массив часов, в которые надо показывать баннер в воскресенье (0-23)   + MONDAY - -||- в понедельник   + TUESDAY - -||- во вторник   + WEDNESDAY - -||- в среду   + THURSDAY - -||- в четверг   + FRIDAY - -||- в пятницу   + SATURDAY - -||- в субботу * arrUSER\_VIEW - массив ID пользователей, для которых доступен просмотр параметров контракта и баннеров и их графики * arrUSER\_ADD - массив ID пользователей, для которых доступен просмотр параметров контракта и управление баннерами * arrUSER\_EDIT - массив ID пользователей, для которых доступно редактирование заголовка и описания контракта, а также возможность назначения прав для просмотра и управления баннерами |
| CONTRACT\_ID | ID контракта, если не указывать - создаётся новый контракт. |
| CHECK\_RIGHTS | Флаг необходимости проверки прав текущего пользователя: "Y" - необходимо проверить права текущего пользователя; "N" - контракт создавать и модифицировать независимо от прав текущего пользователя. Необязательный параметр. |

### Примеры использования

Пример кода, добавляющего новый контракт, либо модифицирующего существующий:

```
<?
if ((strlen($save)>0 || strlen($apply)>0) && $REQUEST_METHOD=="POST")
{
	$arrWEEKDAY = array(
		"SUNDAY"	=> $arrSUNDAY,
		"MONDAY"	=> $arrMONDAY,
		"TUESDAY"	=> $arrTUESDAY,
		"WEDNESDAY"	=> $arrWEDNESDAY,
		"THURSDAY"	=> $arrTHURSDAY,
		"FRIDAY"	=> $arrFRIDAY,
		"SATURDAY"	=> $arrSATURDAY
	);
	$arFields = array(
		"ACTIVE"				=> $ACTIVE,
		"NAME"				  => $NAME,
		"DESCRIPTION"		   => $DESCRIPTION,
		"ADMIN_COMMENTS"		=> $ADMIN_COMMENTS,
		"WEIGHT"				=> $WEIGHT,
		"SORT"				  => $SORT,
		"MAX_SHOW_COUNT"		=> $MAX_SHOW_COUNT,
		"MAX_CLICK_COUNT"	   => $MAX_CLICK_COUNT,
		"DATE_SHOW_FROM"		=> $DATE_SHOW_FROM,
		"DATE_SHOW_TO"		  => $DATE_SHOW_TO,
		"DEFAULT_STATUS_SID"	=> $DEFAULT_STATUS_SID,
		"arrSHOW_PAGE"		  => split("[\n\r]",$SHOW_PAGE),
		"arrNOT_SHOW_PAGE"	  => split("[\n\r]",$NOT_SHOW_PAGE),
		"arrTYPE"			   => $arrTYPE,
		"arrWEEKDAY"			=> $arrWEEKDAY,
		"arrUSER_VIEW"		  => $arrUSER_VIEW,
		"arrUSER_ADD"		   => $arrUSER_ADD,
		"arrUSER_EDIT"		  => $arrUSER_EDIT
	);
	if ($ID = CAdvContract::Set($arFields, $ID))
	{
		if (strlen($strError)<=0)
		{
			if (strlen($save) > 0)
				LocalRedirect("adv_contract_list.php?lang=".LANG);
			else
				LocalRedirect("adv_contract_edit.php?ID=".$ID."&lang=".LANG);
		}
	}
	$DB->PrepareFields("b_adv_contract");
}
?>Копировать
```

Новинки документации в соцсетях:
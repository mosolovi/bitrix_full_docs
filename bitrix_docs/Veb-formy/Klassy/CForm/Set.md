[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

Set (4.0.4)

Set
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
mixed
CForm::Set(
	array fields,
	mixed form_id = false,
	string check_rights = "Y"
)Копировать
```

Добавляет новую [веб-форму](/api_help/form/terms.php#form) или обновляет заданную. Возвращает ID обновленной или добавленной веб-формы в случае положительного результата, в противном случае - "false". Метод нестатический.

**Примечание**  
При обновлении существующей веб-формы (или при добавлении новой веб-формы), автоматически [обновляется](/api_help/form/classes/cform/setmailtemplate.php) тип почтового события (либо [создаётся](/api_help/form/classes/cform/setmailtemplate.php) новый тип).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *fields* | Массив значений полей; в качестве ключей массива допустимы:  * **NAME**\* - заголовок веб-формы; * **SID**\* - символьный идентификатор веб-формы; * **C\_SORT** - индекс сортировки; * **BUTTON** - подпись к кнопке при создании или редактировании результата; * **USE\_RESTRICTIONS** - использовать ограничения; * **RESTRICT\_USER** - максимальное количество результатов от пользователя; * **RESTRICT\_TIME** - минимальный промежуток времени между результатами; * **DESCRIPTION** - описание; * **DESCRIPTION\_TYPE** - тип описания, допустимы следующие значения:   + **text** - текст;   + **html** - HTML код. * **FILTER\_RESULT\_TEMPLATE** - путь относительно корня к файлу, который будет использован для показа фильтра результатов в административной части модуля; * **TABLE\_RESULT\_TEMPLATE** - путь относительно корня к файлу, который будет использован для показа таблицы результатов в административной части модуля; * **STAT\_EVENT1** - идентификатор EVENT1 типа события для модуля "Статистика"; * **STAT\_EVENT2** - идентификатор EVENT2 типа события для модуля "Статистика"; * **STAT\_EVENT3** - дополнительный параметр события для модуля "Статистика"; * **arIMAGE** - массив, описывающий изображение веб-формы, допустимы следующие ключи этого массива:   + **name** - имя файла;   + **size** - размер файла;   + **tmp\_name** - временный путь на сервере;   + **type** - тип загружаемого файла;   + **del** - если значение равно "Y", то изображение будет удалено;   + **MODULE\_ID** - идентификатор модуля "Веб-формы" ("form"). * **USE\_CAPTCHA** - использование капчи, доступны значения:   + **Y** - выводить капчу в публичке,   + **N** - не выводить капчу. * **arSITE** - массив идентификаторов сайтов, к которым будет привязана данная форма:    ```   array("ID_САЙТА_1", "ID_САЙТА_2", ...)Копировать   ``` * **arMAIL\_TEMPLATE** - массив ID почтовых шаблонов, приписанных к данной форме:    ```   array("ID_ШАБЛОНА_1", "ID_ШАБЛОНА_2", ...)Копировать   ```     **Примечание**: Будут привязаны только шаблоны почтового события с идентификатором `FILLING_FORM_[символьный идентификатор веб-формы]` * **arMENU** - массив заголовков меню, отображаемого в административной части и ведущего на результаты данной формы:    ```   array("ID_ЯЗЫКА_1" => "МЕНЮ_1", "ID_ЯЗЫКА_2" => "МЕНЮ_2", ...)Копировать   ``` * **arGROUP** - массив, описывающий права групп пользователей на данную веб-форму:    ```   array("ID_ГРУППЫ_1" => "ПРАВО_1", "ID_ГРУППЫ_2" => "ПРАВО_2", ...)Копировать   ```  \* - обязательно к заполнению. |
| *form\_id* | ID обновляемой веб-формы.  Параметр необязательный. По умолчанию - "false" (добавление новой веб-формы). |
| *check\_rights* | Флаг необходимости проверки прав текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для обновления параметров веб-формы необходимо иметь право **[30] Полный доступ** на форму, указанную в параметре *form\_id*. Для добавления новой веб-формы необходимо иметь право **[W] Полный доступ** на модуль **Веб-формы**.   Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |

### Смотрите также

* [Поля CForm](/api_help/form/classes/cform/index.php)
* [Права на веб-форму](/api_help/form/permissions.php#form)
* [CFile::MakeFileArray](/api_help/main/reference/cfile/makefilearray.php)

### Примеры использования

```
<?
/*************************************************
             Добавление веб-формы
*************************************************/
// создадим массив описывающий изображение 
// находящееся в файле на сервере
$arIMAGE = CFile::MakeFileArray($_SERVER["DOCUMENT_ROOT"]."/images/web_form.gif");
$arIMAGE["MODULE_ID"] = "form";
$arFields = array(
	"NAME"              => "Анкета посетителя",
	"SID"               => "VISITOR_FORM",
	"C_SORT"            => 300,
	"BUTTON"            => "Сохранить",
	"DESCRIPTION"       => "Заполните пож-та анкету",
	"DESCRIPTION_TYPE"  => "text",
	"STAT_EVENT1"       => "form",
	"STAT_EVENT2"       => "visitor_form",
	"arSITE"            => array("r1"),
	"arMENU"            => array("ru" => "Анкета посетителя", "en" => "Visitor Form"),
	"arGROUP"           => array("2" => "15", "3" => "20"),
	"arIMAGE"           => $arIMAGE
);
// добавим новую веб-форму
$NEW_ID = CForm::Set($arFields);
if ($NEW_ID>0) echo "Добавлена веб-форма с ID=".$NEW_ID;
else // ошибка
{
	// выводим текст ошибки
	global $strError;
	echo $strError;
}
?>Копировать
```

```
<?
// пример обновления веб-формы параметры которой были визуально 
// отредактированы в административной части
$w = CGroup::GetList($v1, $v2, Array("ADMIN"=>"N"), $v3);
$arGroups = array();
while ($wr=$w->Fetch()) $arGroups[] = array("ID"=>$wr["ID"], "NAME"=>$wr["NAME"]);
$z = CLanguage::GetList($v1, $v2, array("ACTIVE" => "Y"));
$arFormMenuLang = array();
while ($zr=$z->Fetch()) $arFormMenuLang[] = array("LID"=>$zr["LID"], "NAME"=>$zr["NAME"]);
$rs = CSite::GetList(($by="sort"), ($order="asc"));
while ($ar = $rs->Fetch()) 
{
	if ($ar["DEF"]=="Y") $def_site_id = $ar["ID"];
	$arrSites[$ar["ID"]] = $ar;
}
if ((strlen($save)>0 || strlen($apply)>0) && $REQUEST_METHOD=="POST")
{
	$arIMAGE_ID = $HTTP_POST_FILES["IMAGE_ID"];
	$arIMAGE_ID["MODULE_ID"] = "form";
	$arIMAGE_ID["del"] = ${"IMAGE_ID_del"};
	$arFields = array(
		"NAME"                      => $NAME,
		"SID"                       => $SID,
		"C_SORT"                    => $C_SORT,
		"BUTTON"                    => $BUTTON,
		"DESCRIPTION"               => $DESCRIPTION,
		"DESCRIPTION_TYPE"          => $DESCRIPTION_TYPE,
		"FILTER_RESULT_TEMPLATE"    => $FILTER_RESULT_TEMPLATE,
		"TABLE_RESULT_TEMPLATE"     => $TABLE_RESULT_TEMPLATE,
		"STAT_EVENT1"               => $STAT_EVENT1,
		"STAT_EVENT2"               => $STAT_EVENT2,
		"STAT_EVENT3"               => $STAT_EVENT3,
		"arIMAGE"                   => $arIMAGE_ID,
		"arSITE"                    => $arSITE,
		"arMAIL_TEMPLATE"           => $arMAIL_TEMPLATE
	);
	// меню
	$arMENU = array();
	reset($arFormMenuLang);
	while (list(,$arrL)=each($arFormMenuLang))
	{
		$var = "MENU_".$arrL["LID"];
		global $$var;
		$arMENU[$arrL["LID"]] = $$var;
	}
	$arFields["arMENU"] = $arMENU;
	// права доступа
	$arGROUP = array();
	reset($arGroups);
	while (list(,$arrG)=each($arGroups))
	{
		$var = "PERMISSION_".$arrG["ID"];
		global $$var;
		$arGROUP[$arrG["ID"]] = $$var;
	}
	$arFields["arGROUP"] = $arGROUP;
    
	if ($ID = CForm::Set($arFields, $ID))
	{
		if (strlen($strError)<=0)
		{
			if (strlen($save)>0) LocalRedirect("form_list.php?lang=".LANGUAGE_ID); 
			else LocalRedirect("form_edit.php?ID=".$ID."〈=".LANGUAGE_ID);
		}
	}
	$DB->PrepareFields("b_form");
}
?>Копировать
```

Новинки документации в соцсетях:
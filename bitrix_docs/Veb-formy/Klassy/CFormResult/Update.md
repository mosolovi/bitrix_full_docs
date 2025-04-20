[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

Update (3.3.10)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CFormResult::Update(
	int result_id,
	array values = false,
	string update_fields = "N",
	string check_rights = "Y"
)Копировать
```

Обновляет все значения [ответов](/api_help/form/terms.php#answer) и [полей](/api_help/form/terms.php#field) [результата](/api_help/form/terms.php#result) веб-формы. В случае успеха возвращает "true", в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *result\_id* | ID [результата](/api_help/form/terms.php#result). |
| *values* | Массив со значениями [ответов](/api_help/form/terms.php#answer) и [полей](/api_help/form/terms.php#field) веб-формы. Массив имеет следующую структуру:  ``` array( 	"имя HTML поля 1" => "значение 1", 	"имя HTML поля 2" => "значение 2", 	... 	"имя HTML поля N" => "значение N" )Копировать ```  Правила формирования "*имен HTML полей*" и "*значений*" можно посмотреть [здесь](/api_help/form/htmlnames.php).Пример:  ``` Array ( 	[form_text_586] => Иванов Иван Иванович 	[form_date_587] => 10.03.1992 	[form_textarea_588] => г. Мурманск 	[form_radio_VS_MARRIED] => 589 	[form_checkbox_VS_INTEREST] => Array 	( 		[0] => 592 		[1] => 593 		[2] => 594 	) 	[form_dropdown_VS_AGE] => 597 	[form_multiselect_VS_EDUCATION] => Array 	( 		[0] => 603 		[1] => 604 	) 	[form_text_606] => 2345 	[form_image_607] => 1045 	[form_textarea_ADDITIONAL_149] => 155 )Копировать ```  Параметр необязательный. По умолчанию - "false" (будет взят стандартный массив $\_REQUEST). |
| *update\_fiels* | Флаг необходимости обновления [полей](/api_help/form/terms.php#field) веб-формы. Возможны следующие значения:  * **Y** - необходимо обновить; * **N** - не нужно обновлять.  Параметр необязательный. По умолчанию - "N" (не нужно обновлять). |
| *check\_rights* | Флаг необходимости проверки прав текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - права не нужно проверять.  Для успешного обновления [результата](/api_help/form/terms.php#result) необходимо обладать следующими [правами](/api_help/form/permissions.php):  1. На веб-форму, к которой принадлежит редактируемый результат:          **[20] Работа со всеми результатами в соответствии с их статусами**          или, в случае, если вы являетесь создателем редактируемого результата, достаточно права:          **[15] Работа со своим результатом в соответствии с его статусом** 2. На статус, в котором находится редактируемый результат, необходимо иметь право:          **[EDIT] редактирование**  Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |

### Смотрите также

* [CFormResult::SetField](/api_help/form/classes/cformresult/setfield.php)
* [CFormResult::GetDataByIDForHTML](/api_help/form/classes/cformresult/getdatabyidforhtml.php)
* [CFormResult::Add](/api_help/form/classes/cformresult/add.php)

### Примеры использования

```
<?
// ID результата
$RESULT_ID = 186;
// массив описывающий загруженную на сервер фотографию
$arImage = CFile::MakeFileArray($_SERVER["DOCUMENT_ROOT"]."/images/photo.gif");
// массив значений ответов и полей веб-формы
$arValues = array (
	"form_text_586"                 => "Иванов Иван",    // "Фамилия, имя, отчество"
	"form_date_587"                 => "01.06.1904",     // "Дата рождения"
	"form_textarea_588"             => "г. Москва",      // "Адрес"
	"form_radio_VS_MARRIED"         => 590,              // "Женаты/замужем?"
	"form_checkbox_VS_INTEREST"     => array(612, 613),  // "Увлечения"
	"form_dropdown_VS_AGE"          => 601,              // "Возраст"
	"form_multiselect_VS_EDUCATION" => array(602, 603),  // "Образование"
	"form_text_606"                 => 300,              // "Доход"
	"form_image_607"                => $arImage,         // "Фотография"
	"form_textarea_ADDITIONAL_149"  => "155 рублей"      // "Рассчитанная сумма"
)
//обновим результат
if (CFormResult::Update($RESULT_ID, $arValues, "Y"))
{
	echo "Результат #".$RESULT_ID." успешно обновлен.";
}
else
{
	global $strError;
	echo $strError;
}
?>Копировать
```

Новинки документации в соцсетях:
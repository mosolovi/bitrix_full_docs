[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

Add (3.3.10)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
mixed
CFormResult::Add(
	int form_id,
	array values = false,
	string check_rights = "Y",
	int user_id = false
)Копировать
```

Создает новый [результат](/api_help/form/terms.php#result) веб-формы. В случае успеха - возвращает ID нового [результата](/api_help/form/terms.php#result), в противном случае - "false". Метод нестатический.

Данный метод не создает почтовое событие, связанное с формой. Для этого нужно использовать [CFormResult::Mail](/api_help/form/classes/cformresult/mail.php).

**Примечание:** в случае неактивных вопросов данные из формы в них не сохраняются и сообщения об ошибках не выводятся.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *form\_id* | ID веб-формы. |
| *values* | Массив со значениями [ответов](/api_help/form/terms.php#answer). Массив имеет следующую структуру:  ``` array( 	"имя HTML поля ответа 1" => "значение ответа 1", 	"имя HTML поля ответа 2" => "значение ответа 2", 	... 	"имя HTML поля ответа N" => "значение ответа N" )Копировать ```  Правила формирования "*имен HTML полей ответов*" и "*значений ответов*" описаны в разделе "[Имена HTML полей веб-форм](/api_help/form/htmlnames.php)".Пример:  ``` Array ( 	[form_text_586] => Иванов Иван Иванович 	[form_date_587] => 10.03.1992 	[form_textarea_588] => г. Мурманск 	[form_radio_VS_MARRIED] => 589 	[form_checkbox_VS_INTEREST] => Array 	( 		[0] => 592 		[1] => 593 		[2] => 594 	) 	[form_dropdown_VS_AGE] => 597 	[form_multiselect_VS_EDUCATION] => Array 	( 		[0] => 603 		[1] => 604 	) 	[form_text_606] => 2345 	[form_image_607] => 1045 )Копировать ```  Параметр необязательный. По умолчанию - "false" (будет взят стандартный массив $\_REQUEST). |
| *check\_rights* | Флаг необходимости проверки прав текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для создания нового [результата](/api_help/form/terms.php#result) необходимо иметь право **[10] Заполнение веб-формы** на веб-форму *form\_id*.   Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |
| *user\_id* | ID пользователя, который будет записан как создатель данного [результата](/api_help/form/terms.php#result).   Параметр необязательный. По умолчанию - "false" (будет взят ID текущего пользователя). |

### Смотрите также

* [CFormResult::Update](/api_help/form/classes/cformresult/update.php)
* [CFormResult::SetField](/api_help/form/classes/cformresult/setfield.php);
* [CFormResult::GetDataByIDForHTML](/api_help/form/classes/cformresult/getdatabyidforhtml.php)

### Примеры использования

```
<?
// ID веб-формы
$FORM_ID = 4;
// массив описывающий загруженную на сервер фотографию
$arImage = CFile::MakeFileArray($_SERVER["DOCUMENT_ROOT"]."/images/photo.gif");
// массив значений ответов
$arValues = array (
	"form_text_586"                 => "Иванов Иван",    // "Фамилия, имя, отчество"
	"form_date_587"                 => "01.06.1904",     // "Дата рождения"
	"form_textarea_588"             => "г. Москва",      // "Адрес"
	"form_radio_VS_MARRIED"         => 590,              // "Женаты/замужем?"
	"form_checkbox_VS_INTEREST"     => array(612, 613),  // "Увлечения"
	"form_dropdown_VS_AGE"          => 601,              // "Возраст"
	"form_multiselect_VS_EDUCATION" => array(602, 603),  // "Образование"
	"form_text_606"                 => 300,              // "Доход"
	"form_image_607"                => $arImage          // "Фотография"
);
// создадим новый результат
if ($RESULT_ID = CFormResult::Add($FORM_ID, $arValues))
{
	echo "Результат #".$RESULT_ID." успешно создан";
}
else
{
	global $strError;
	echo $strError;
}
?>Копировать
```

Новинки документации в соцсетях:
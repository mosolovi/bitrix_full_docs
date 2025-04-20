[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

GetDataByIDForHTML (4.0.4)

GetDataByIDForHTML
==================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CFormResult::GetDataByIDForHTML(
	int result_id,
	string get_fields = "N"
)Копировать
```

Возвращает массив значений [ответов](/api_help/form/terms.php#answer) на [вопросы](/api_help/form/terms.php#question) веб-формы, а также значения [полей](/api_help/form/terms.php#field) веб-формы для указанного [результата](/api_help/form/terms.php#result). Метод нестатический.

Ключи возвращаемого массива в точности соответствуют [правилам](/api_help/form/htmlnames.php) формирования имен HTML полей для веб-формы.

Пример массива, возвращаемого методом:

```
Array
(
	[form_text_586] => Иванов Иван Иванович
	[form_date_587] => 10.03.1992
	[form_textarea_588] => г. Мурманск
	[form_radio_VS_MARRIED] => 589
	[form_checkbox_VS_INTEREST] => Array
		(
			[0] => 592
			[1] => 593
			[2] => 594
		)
	[form_dropdown_VS_AGE] => 597
	[form_multiselect_VS_EDUCATION] => Array
		(
			[0] => 603
			[1] => 604
		)
	[form_text_606] => 2345
	[form_image_607] => 1045
)Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *result\_id* | ID результата. |
| *get\_fields* | Если значение данного параметра равно "Y", то в в массиве, возвращаемом данным методом, будут также значения [полей](/api_help/form/terms.php#field) веб-формы; в противном случае, в возвращаемом массиве будут только значения [ответов](/api_help/form/terms.php#answer) на [вопросов](/api_help/form/terms.php#question) веб-формы.   Параметр необязательный. По умолчанию - "N". |

### Смотрите также

* [Имена HTML полей](/api_help/form/htmlnames.php)
* [CFormResult::Add](/api_help/form/classes/cformresult/add.php)
* [CFormResult::Update](/api_help/form/classes/cformresult/update.php)
* [CForm::Check](/api_help/form/classes/cform/check.php)

### Примеры использования

```
<?
$RESULT_ID = 189; // ID результата
// получим данные результата
$arValues = CFormResult::GetDataByIDForHTML($RESULT_ID, "Y");
// выведем ответ на вопрос "Фамилия, имя, отчество"
echo $arValues["form_text_586"]; // "Иванов Василий"
// выведем фотографию загруженную в качестве ответа на вопрос "Фотография"
CFile::ShowImage($arValues["form_image_607"], 200, 200, "border=0", "", true);
// выведем значение поля веб-формы "Рассчитанная стоимость"
echo $arValues["form_textarea_ADDITIONAL_149"]; // 134 руб.
?>Копировать
```

Новинки документации в соцсетях:
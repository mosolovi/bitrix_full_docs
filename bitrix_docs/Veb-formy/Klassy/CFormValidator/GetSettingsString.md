[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormValidator](/api_help/form/classes/cformvalidator/index.php)

GetSettingsString (6.0.0)

GetSettingsString
=================

```
string
CFormValidator::GetSettingsString(
	array arValidator,
	array arParams
)Копировать
```

Возвращает список настроек валидатора со значениями, преобразованный для занесения в базу. Аналогичен прямому вызову метода преобразования настроек (`CONVERT_TO_DB`) валидатора. При вызове методов [CFormValidator::Set](/api_help/form/classes/cformvalidator/getlist.php) и [CFormValidator::SetBatch](/api_help/form/classes/cformvalidator/getlistform.php) вызывается автоматически. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *arValidator* | Описательный массив валидатора (например, полученный из результата метода CFormValidators::GetList). |
| *arParams* | Массив значений настроек валидатора. |

Новинки документации в соцсетях:
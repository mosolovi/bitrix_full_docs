[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormValidator](/api_help/form/classes/cformvalidator/index.php)

GetSettingsArray (6.0.0)

GetSettingsArray
================

```
array
CFormValidator::GetSettingsArray(
	array arValidator,
	string strParams
)Копировать
```

Возвращает список настроек валидатора со значениями после обратного преобразования строки, занесенной в базу. Аналогичен прямому вызову метода обратного преобразования (`CONVERT_FROM_DB`) валидатора. При вызове методов [CFormValidator::GetList](/api_help/form/classes/cformvalidator/getlist.php) и [CFormValidator::GetListForm](/api_help/form/classes/cformvalidator/getlistform.php) вызывается автоматически. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *arValidator* | Описательный массив валидатора (например, полученный из результата метода CFormValidators::GetList). |
| *strParams* | Строка со значениями настроек, хранящаяся в БД. |

Новинки документации в соцсетях:
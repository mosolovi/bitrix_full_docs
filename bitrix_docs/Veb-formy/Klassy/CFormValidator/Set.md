[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormValidator](/api_help/form/classes/cformvalidator/index.php)

Set (6.0.0)

Set
===

```
bool
CFormValidator::Set(
	int WEB_FORM_ID,
	int FIELD_ID,
	string VALIDATOR_SID,
	array arParams = array(),
)Копировать
```

Прикрепляет валидатор с заданными настройками к полю формы. Возвращает true в случае успеха операции и false в случае ошибки (валидатора с таким ID не существует, ошибка в валидаторе и т.д.). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *WEB\_FORM\_ID* | ID [веб-формы](/api_help/form/terms.php#form). |
| *FIELD\_ID* | ID [вопроса](/api_help/form/terms.php#question). |
| *VALIDATOR\_SID* | Идентификатор валидатора. |
| *arParams* | Массив значений параметров валидатора. Необязательный параметр. |
| *c\_sort* | Необязательный параметр. Значение по умолчанию - 100. |

Новинки документации в соцсетях:
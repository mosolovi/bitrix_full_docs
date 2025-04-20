[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormValidator](/api_help/form/classes/cformvalidator/index.php)

SetBatch (6.0.0)

SetBatch
========

```
CFormValidator::SetBatch(
	int WEB_FORM_ID,
	int FIELD_ID,
	array arValidators = array(),
)Копировать
```

Прикрепляет группу валидаторов с заданными настройками к полю формы. Аналогична вызову [CFormValidator::Set](/api_help/form/classes/cformvalidator/set.php) для каждого валидатора группы. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *WEB\_FORM\_ID* | ID [веб-формы](/api_help/form/terms.php#form). |
| *FIELD\_ID* | ID [вопроса](/api_help/form/terms.php#question). |
| *arValidators* | Массив валидаторов. Каждый элемент массива должен представлять собой ассоциативный массив с ключами:  * **NAME** - идентификатор валидатора; * **PARAMS** - массив параметрова валидатора. |

Новинки документации в соцсетях:
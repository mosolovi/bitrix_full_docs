[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

SetInputDefaultValue (5.9.2)

SetInputDefaultValue
====================

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
void
CFormOutput::SetInputDefaultValue(
	string $FIELD_SID,
	mixed $value [,
	mixed $ANSWER_ID = false] 
);Копировать
```

Устанавливает значение *по умолчанию* для поля веб-формы. Данный метод используется только с визуальным шаблоном веб-формы. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *FIELD\_SID* | Строковой идентификатор вопроса. |
| *value* | Значение ответа (или идентификатор ответа для вопросов с вариантами (radio, checkbox, multiselect, dropdown)). Для типов вопросов, подразумевающих возможность множественного выбора (checkbox, multiselect) можно передавать массив идентфикаторов. |
| *ANSWER\_ID* | Необязательный параметр. Массив идентификаторов ответа или идентификатор ответа (используется для множественных полей). |

### Пример использования

```
// использование в компоненте form.result.new
$FORM = new CFormOutput();
$FORM->InitializeTemplate($arParams, $arResult);
/* .............. */ 
$FORM->setInputDefaultValue('MY_TEXT_FIELD', $USER->GetFullName()); // для простых строк 
$FORM->setInputDefaultValue('MY_CHECKBOX_FIELD', "Y", array(1114, 1115)); // для checkbox или multiselect.
// или $FORM->setInputDefaultValue('MY_CHECKBOX_FIELD', array(1114, 1115)); 
$FORM->setInputDefaultValue('MY_RADIO_FIELD', "Y", 1103); // для radio 
// или $FORM->setInputDefaultValue('MY_RADIO_FIELD', 1103); 
// 1103-1115 - идентификаторы ответов.
/* .............. */ 
$strReturn = $FORM->IncludeFormCustomTemplate()Копировать
```

Новинки документации в соцсетях:
[Веб-формы](/api_help/form/index.php)

Имена HTML полей веб-форм

Имена HTML полей веб-форм
=========================

Включить вкладки

Вопросы веб-формы

Поля веб-формы

Смотрите также

### Вопросы веб-формы

При выводе веб-формы все [ответы](/api_help/form/terms.php#answer) на [вопросы](/api_help/form/terms.php#question) представляются в виде HTML полей, заполняя которые,
пользователи отвечают на тот или иной вопрос. Ниже представлена таблица зависимости имен HTML-полей от типов ответов.

| Тип ответа | Описание | Имя HTML поля | Значение ответа |
| --- | --- | --- | --- |
| text | Однострочное текстовое поле. | form\_text\_*answer\_id* | Текст, введенный с клавиатуры. |
| textarea | Многострочное текстовое поле. | form\_textarea\_*answer\_id* | Текст, введенный с клавиатуры. |
| password | Однострочное текстовое поле для ввода пароля. | form\_password\_*answer\_id* | Текст, введенный с клавиатуры. |
| date | Однострочное текстовое поле для ввода даты. | form\_date\_*answer\_id* | Текст, введенный с клавиатуры. |
| radio | Переключатель одиночного выбора. | form\_radio\_*question\_sid* | ID выбранного ответа. |
| dropdown | Выпадающий список одиночного выбора. | form\_dropdown\_*question\_sid* | ID выбранного ответа. |
| checkbox | Флаг множественного выбора. | form\_checkbox\_*question\_sid*[] | Массив ID выбранных ответов. |
| multiselect | Список множественного выбора. | form\_multiselect\_*question\_sid*[] | Массив ID выбранных ответов. |
| file | Поле для ввода произвольного файла. | form\_file\_*answer\_id* | Массив, описывающий загруженный файл. |
| image | Поле для ввода изображения. | form\_image\_*answer\_id* | Массив, описывающий загруженный файл. |
| hidden **\*** | Скрытое поле. | form\_hidden\_*answer\_id* | Данные из скрытого поля формы. |
| **\*** - доступно только для упрощенного режима редактирования веб-форм | | | |

###### Принятые обозначения

* *answer\_id* - ID [ответа](/api_help/form/terms.php#answer);
* *question\_sid* - символьный идентификатор [вопроса](/api_help/form/terms.php#question).

### Поля веб-формы

Помимо ответов на вопросы веб-формы, необходимо выводить и редактировать значения [полей](/api_help/form/terms.php#field) веб-формы. Ниже представлена таблица зависимости имен HTML полей от типов поля веб-формы.

| Тип поля | Описание | Имя HTML поля | Значение |
| --- | --- | --- | --- |
| text | Текст | form\_textarea\_ADDITIONAL\_*field\_id* | Текст, введенный с клавиатуры. |
| integer | Число | form\_text\_ADDITIONAL\_*field\_id* | Текст, введенный с клавиатуры. |
| date | Дата | form\_date\_ADDITIONAL\_*field\_id* | Текст, введенный с клавиатуры. |

###### Принятые обозначения

* *field\_id* - ID [поля](/api_help/form/terms.php#field) веб-формы.

### Смотрите также

* [CForm::GetTextField](/api_help/form/classes/cform/gettextfield.php)
* [CForm::GetTextAreaField](/api_help/form/classes/cform/gettextareafield.php)
* [CForm::GetPasswordField](/api_help/form/classes/cform/getpasswordfield.php)
* [CForm::GetDateField](/api_help/form/classes/cform/getdatefield.php)
* [CForm::GetRadioField](/api_help/form/classes/cform/getradiofield.php)
* [CForm::GetCheckBoxField](/api_help/form/classes/cform/getcheckboxfield.php)
* [CForm::GetDropDownField](/api_help/form/classes/cform/getdropdownfield.php)
* [CForm::GetMultiSelectField](/api_help/form/classes/cform/getmultiselectfield.php)
* [CForm::GetFileField](/api_help/form/classes/cform/getfilefield.php)
* [CFormResult::GetDataByIDForHTML](/api_help/form/classes/cformresult/getdatabyidforhtml.php)

Новинки документации в соцсетях:
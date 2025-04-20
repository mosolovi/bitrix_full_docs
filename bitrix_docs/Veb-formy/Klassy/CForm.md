[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

Класс CForm (3.1.1)

Класс CForm
===========

Включить вкладки

Поля

Методы для работы с веб-формой

Методы, возвращающие HTML код полей фильтра

Методы, возвращающие HTML код полей для ввода ответов на вопросы веб-формы

Методы получения текущего значения поля

Дополнительные методы

**CForm** - класс для работы с [веб-формами](/api_help/form/terms.php#form).

### Поля

| Поле | Тип | Описание |
| --- | --- | --- |
| ID | int | Идентификатор [веб-формы](/api_help/form/terms.php#form). |
| SID | varchar(50) | Символьный идентификатор [веб-формы](/api_help/form/terms.php#form). |
| TIMESTAMP\_X | datetime | Время последнего изменения [веб-формы](/api_help/form/terms.php#form). |
| NAME | varchar(255) | Заголовок [веб-формы](/api_help/form/terms.php#form). |
| BUTTON | varchar(255) | Подпись на кнопки при заполнении [веб-формы](/api_help/form/terms.php#form) или редактировании [результата](/api_help/form/terms.php#result). |
| C\_SORT | int | Индекс сортировки. |
| IMAGE\_ID | int | ID изображения [веб-формы](/api_help/form/terms.php#form). |
| DESCRIPTION | varchar(2000) | Описание [веб-формы](/api_help/form/terms.php#form). |
| DESCRIPTION\_TYPE | varchar(4) | Тип описания [веб-формы](/api_help/form/terms.php#form) ("text" или "html"). |
| MAIL\_EVENT\_TYPE | varchar(50) | Идентификатор типа почтового события. |
| FILTER\_RESULT\_TEMPLATE | varchar(2000) | Путь к скрипту, отображающему фильтр по [результатам](/api_help/form/terms.php#result) [веб-форм](/api_help/form/terms.php#form) в административной части модуля. |
| TABLE\_RESULT\_TEMPLATE | varchar(2000) | Путь к скрипту, отображающему таблицу [результатов](/api_help/form/terms.php#result) [веб-форм](/api_help/form/terms.php#form) в административной части модуля. |
| STAT\_EVENT1 | varchar(255) | Идентификатор EVENT1 типа события для модуля "[Статистика](../../../../../../statistic/help/ru/index.php.html)". |
| STAT\_EVENT2 | varchar(255) | Идентификатор EVENT2 типа события для модуля "[Статистика](../../../../../../statistic/help/ru/index.php.html)". |
| STAT\_EVENT3 | varchar(255) | Дополнительный параметр события для модуля "[Статистика](../../../../../../statistic/help/ru/index.php.html)". |

### Методы для работы с веб-формой

| Метод | Описание | С версии |
| --- | --- | --- |
| [Set](/api_help/form/classes/cform/set.php) | Добавляет новую [веб-форму](/api_help/form/terms.php#form), либо обновляет параметры существующей. | 4.0.4 |
| [SetMailTemplate](/api_help/form/classes/cform/setmailtemplate.php) | Создает тип почтового события и почтовые шаблоны для [веб-формы](/api_help/form/terms.php#form). |  |
| [GetList](/api_help/form/classes/cform/getlist.php) | Возвращает список [веб-форм](/api_help/form/terms.php#form). |  |
| [GetByID](/api_help/form/classes/cform/getbyid.php) | Возвращает параметры [веб-формы](/api_help/form/terms.php#form) по ее цифровому идентификатору. |  |
| [GetBySID](/api_help/form/classes/cform/getbysid.php) | Возвращает параметры [веб-формы](/api_help/form/terms.php#form) по ее символьному идентификатору. | 3.3.10 |
| [GetDataByID](/api_help/form/classes/cform/getdatabyid.php) | Возвращает массивы, описывающие [вопросы](/api_help/form/terms.php#question) и [поля](/api_help/form/terms.php#field) [веб-формы](/api_help/form/terms.php#form). |  |
| [GetResultAnswerArray](/api_help/form/classes/cform/getresultanswerarray.php) | Возвращает массивы, описывающие [вопросы](/api_help/form/terms.php#question) и [поля](/api_help/form/terms.php#field) [веб-формы](/api_help/form/terms.php#form), а также [ответы](/api_help/form/terms.php#answer) и их значения. |  |
| [GetPermission](/api_help/form/classes/cform/getpermission.php) | Возвращает [право](/api_help/form/permissions.php#form) пользователя на [веб-форму](/api_help/form/terms.php#form). |  |
| [Copy](/api_help/form/classes/cform/copy.php) | Копирует [веб-форму](/api_help/form/terms.php#form). | 4.0.4 |
| [Reset](/api_help/form/classes/cform/reset.php) | Удаляет все [результаты](/api_help/form/terms.php#result) [веб-формы](/api_help/form/terms.php#form). |  |
| [Delete](/api_help/form/classes/cform/delete.php) | Удаляет [веб-форму](/api_help/form/terms.php#form) и все ее [результаты](/api_help/form/terms.php#result). |  |
| [Check](/api_help/form/classes/cform/check.php) | Проверяет введенные значения на обязательность, правильность формата даты и правильность типа файла. |  |

### Методы, возвращающие HTML код полей фильтра

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetTextFilter](/api_help/form/classes/cform/gettextfilter.php) | Однострочное текстовое поле для фильтрации текстовых значений. |  |
| [GetDateFilter](/api_help/form/classes/cform/getdatefilter.php) | Два поля для ввода интервала дат. |  |
| [GetDropDownFilter](/api_help/form/classes/cform/getdropdownfilter.php) | Выпадающий список одиночного выбора. |  |
| [GetNumberFilter](/api_help/form/classes/cform/getnumberfilter.php) | Два поля для ввода числового интервала. |  |
| [GetExistFlagFilter](/api_help/form/classes/cform/getexistflagfilter.php) | Флаг, используемый для фильтрации по факту существования [ответа](/api_help/form/terms.php#answer) на [вопрос](/api_help/form/terms.php#question). | 4.0.4 |

### Методы, возвращающие HTML код полей для ввода ответов на вопросы веб-формы

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetTextField](/api_help/form/classes/cform/gettextfield.php) | Однострочное текстовое поле для ввода текста. |  |
| [GetTextAreaField](/api_help/form/classes/cform/gettextareafield.php) | Многострочное текстовое поле для ввода текста. |  |
| [GetPasswordField](/api_help/form/classes/cform/getpasswordfield.php) | Однострочное текстовое поле для ввода пароля. | 3.3.0 |
| [GetDateField](/api_help/form/classes/cform/getdatefield.php) | Поле для ввода даты. |  |
| [GetRadioField](/api_help/form/classes/cform/getradiofield.php) | Переключатель одиночного выбора. |  |
| [GetCheckBoxField](/api_help/form/classes/cform/getcheckboxfield.php) | Флаг множественного выбора. |  |
| [GetDropDownField](/api_help/form/classes/cform/getcheckboxfield.php) | Выпадающий список одиночного выбора. |  |
| [GetMultiSelectField](/api_help/form/classes/cform/getmultiselectfield.php) | Список множественного выбора. |  |
| [GetFileField](/api_help/form/classes/cform/getfilefield.php) | Поле для ввода файла. |  |

### Методы получения текущего значения поля

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetTextValue](/api_help/form/classes/cform/gettextvalue.php) | Возвращает текущее значение для однострочного текстового поля. |  |
| [GetTextAreaValue](/api_help/form/classes/cform/gettextareavalue.php) | Возвращает текущее значение для многострочного текстового поля. |  |
| [GetPasswordValue](/api_help/form/classes/cform/gettextareavalue.php) | Возвращает текущее значение для поля ввода пароля. | 3.3.0 |
| [GetDateValue](/api_help/form/classes/cform/getdatevalue.php) | Возвращает текущее значение для поля ввода даты. |  |
| [GetRadioValue](/api_help/form/classes/cform/getradiovalue.php) | Возвращает текущее значение для переключателя одиночного выбора. |  |
| [GetCheckBoxValue](/api_help/form/classes/cform/getcheckboxvalue.php) | Возвращает текущее значение для флага множественного выбора. |  |
| [GetDropDownValue](/api_help/form/classes/cform/getdropdownvalue.php) | Возвращает текущее значение для выпадающего списка одиночного выбора. |  |
| [GetMultiSelectValue](/api_help/form/classes/cform/getmultiselectvalue.php) | Возвращает текущее значение для списка множественного выбора. |  |

### Дополнительные методы

| Метод | Описание | С версии |
| --- | --- | --- |
| [IsAdmin](/api_help/form/classes/cform/isadmin.php) | Возвращает "true", если текущий пользователь имеет административные права на модуль **Веб-формы**, в противном случае - "false". | 4.0.4 |

Новинки документации в соцсетях:
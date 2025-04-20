[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormField](/api_help/form/classes/cformfield/index.php)

Класс CFormField (4.0.4)

Класс CFormField
================

Включить вкладки

Поля

Методы

**CFormField** - класс для работы с [вопросами](/api_help/form/terms.php#question) и [полями](/api_help/form/terms.php#field).

### Поля

| Поле | Тип | Описание |
| --- | --- | --- |
| ID | int | Идентификатор [вопроса](/api_help/form/terms.php#question) / [поля](/api_help/form/terms.php#field). |
| SID | varchar(50) | Символьный идентификатор [вопроса](/api_help/form/terms.php#question) / [поля](/api_help/form/terms.php#field). |
| FORM\_ID | int | ID [веб-формы](/api_help/form/terms.php#form), к которой приписан данный [вопрос](/api_help/form/terms.php#question) / [поле](/api_help/form/terms.php#field). |
| TIMESTAMP\_X | datetime | Время последнего изменения параметров [вопроса](/api_help/form/terms.php#question) / [поля](/api_help/form/terms.php#field). |
| ACTIVE | char | Флаг активности (Y|N). |
| ADDITIONAL | char | Если в данном флаге хранится значение "Y", то данная запись является [полем](/api_help/form/terms.php#field), иначе это [вопрос](/api_help/form/terms.php#question) [веб-формы](/api_help/form/terms.php#form). |
| FIELD\_TYPE | varchar(50) | Тип [поля](/api_help/form/terms.php#field), допустимы следующие значения:  * **text** - текст; * **integer** - число; * **date** - дата. |
| TITLE | varchar(2000) | Текст [вопроса](/api_help/form/terms.php#question) или заголовок [поля](/api_help/form/terms.php#field). |
| TITLE\_TYPE | varchar(4) | Тип текста [вопроса](/api_help/form/terms.php#question) ("text" или "html"). |
| IMAGE\_ID | int | Изображение [вопроса](/api_help/form/terms.php#question). |
| C\_SORT | int | Индекс сортировки. |
| REQUIRED | char | Флаг обязательности [ответа](/api_help/form/terms.php#answer) на [вопрос](/api_help/form/terms.php#question) при создании нового или редактировании существующего [результата](/api_help/form/terms.php#result) (Y|N). |
| IN\_FILTER | char | Означает, что данный [вопрос](/api_help/form/terms.php#question) / [поле](/api_help/form/terms.php#field) входят в фильтр по [результатам](/api_help/form/terms.php#result). |
| FILTER\_TITLE | varchar(2000) | Подпись к полю фильтра. |
| IN\_RESULTS\_TABLE | char | Если в данном флаге хранится значение "Y", значение данного [вопроса](/api_help/form/terms.php#question) / [поля](/api_help/form/terms.php#field) будет отображено в HTML таблице [результатов](/api_help/form/terms.php#result). |
| IN\_EXCEL\_TABLE | char | Если в данном флаге хранится значение "Y", значение данного [вопроса](/api_help/form/terms.php#question) / [поля](/api_help/form/terms.php#field) будет отображено в Excel таблице [результатов](/api_help/form/terms.php#result). |
| RESULTS\_TABLE\_TITLE | varchar(2000) | Заголовок столбца в таблице [результатов](/api_help/form/terms.php#result). |
| COMMENTS | varchar(2000) | Служебный комментарий к [вопросу](/api_help/form/terms.php#question) / [полю](/api_help/form/terms.php#field). |

### Методы

| Метод | Описание | С версии |
| --- | --- | --- |
| [Set](/api_help/form/classes/cformfield/set.php) | Добавляет новый [вопрос](/api_help/form/terms.php#question) / [поле](/api_help/form/terms.php#field), либо обновляет параметры существующего. |  |
| [GetList](/api_help/form/classes/cformfield/getlist.php) | Возвращает список [вопросов](/api_help/form/terms.php#question) / [полей](/api_help/form/terms.php#field). |  |
| [GetByID](/api_help/form/classes/cformfield/getbyid.php) | Возвращает параметры [вопроса](/api_help/form/terms.php#question) / [поля](/api_help/form/terms.php#field) по цифровому идентификатору. |  |
| [GetBySID](/api_help/form/classes/cformfield/getbysid.php) | Возвращает параметры [вопроса](/api_help/form/terms.php#question) / [поля](/api_help/form/terms.php#field) по символьному идентификатору. |  |
| [Copy](/api_help/form/classes/cformfield/copy.php) | Копирует [вопрос](/api_help/form/terms.php#question) / [поле](/api_help/form/terms.php#field). |  |
| [Reset](/api_help/form/classes/cformfield/reset.php) | Удаляет все значения ответов на [вопрос](/api_help/form/terms.php#question) / [поле](/api_help/form/terms.php#field) из [результатов](/api_help/form/terms.php#result). |  |
| [Delete](/api_help/form/classes/cformfield/delete.php) | Удаляет [вопрос](/api_help/form/terms.php#question) / [поле](/api_help/form/terms.php#field), а также все значения ответов на него из [результатов](/api_help/form/terms.php#result). |  |

Новинки документации в соцсетях:
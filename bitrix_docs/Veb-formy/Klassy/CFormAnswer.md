[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormAnswer](/api_help/form/classes/cformanswer/index.php)

Класс CFormAnswer (4.0.4)

Класс CFormAnswer
=================

Включить вкладки

Поля

Методы

**CFormAnswer** - класс для работы с [ответами](/api_help/form/terms.php#answer).

### Поля

| Поле | Тип | Описание |
| --- | --- | --- |
| ID | int | Идентификатор [ответа](/api_help/form/terms.php#answer). |
| FIELD\_ID | int | Идентификатор [вопроса](/api_help/form/terms.php#question) (синоним данного поля - QUESTION\_ID). |
| TIMESTAMP\_X | datetime | Время последнего изменения параметров [ответа](/api_help/form/terms.php#answer). |
| MESSAGE | varchar(2000) | Значение параметра [ответа](/api_help/form/terms.php#answer) ANSWER\_TEXT. |
| VALUE | varchar(255) | Значение параметра [ответа](/api_help/form/terms.php#answer) ANSWER\_VALUE. |
| FIELD\_TYPE | varchar(255) | Тип поля [ответа](/api_help/form/terms.php#answer), допустимы следующие значения:  * **text** - однострочное текстовое поле; * **textarea** - многострочное текстовое поле; * **radio** - переключатель одиночного выбора (radio-кнопка); * **checkbox** - флаг множественного выбора (checkbox); * **dropdown** - элемент выпадающего списка одиночного выбора; * **multiselect** - элемент списка множественного выбора; * **date** - поле для ввода даты; * **image** - поле для загрузки изображения; * **file** - поле для загрузки произвольного файла; * **password** - поле для ввода пароля. |
| FIELD\_WIDTH | int | Ширина поля [ответа](/api_help/form/terms.php#answer). |
| FIELD\_HEIGHT | int | Высота поля [ответа](/api_help/form/terms.php#answer). |
| FIELD\_PARAM | varchar(2000) | Параметры поля [ответа](/api_help/form/terms.php#answer). |
| C\_SORT | int | Индекс сортировки. |
| ACTIVE | char | Флаг активности (Y|N). |

### Методы

| Метод | Описание |
| --- | --- |
| [Set](/api_help/form/classes/cformanswer/set.php) | Добавляет новый [ответ](/api_help/form/terms.php#answer), либо обновляет параметры существующего. |
| [GetList](/api_help/form/classes/cformanswer/getlist.php) | Возвращает список [ответов](/api_help/form/terms.php#answer) по указанному [вопросу](/api_help/form/terms.php#question). |
| [GetByID](/api_help/form/classes/cformanswer/getbyid.php) | Возвращает параметры [ответа](/api_help/form/terms.php#answer). |
| [Copy](/api_help/form/classes/cformanswer/copy.php) | Копирует [ответ](/api_help/form/terms.php#answer). |
| [Delete](/api_help/form/classes/cformanswer/delete.php) | Удаляет [ответ](/api_help/form/terms.php#answer) и все значения в [результатах](/api_help/form/terms.php#result), связанные с данным ответом. |

Новинки документации в соцсетях:
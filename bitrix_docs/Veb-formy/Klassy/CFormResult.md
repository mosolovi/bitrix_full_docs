[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

Класс CFormResult (3.3.10)

Класс CFormResult
=================

Включить вкладки

Поля

Методы

**CFormResult** - класс для работы с [результатами](/api_help/form/terms.php#result).

### Поля

| Поле | Тип | Описание |
| --- | --- | --- |
| ID | int | Идентификатор результата. |
| FORM\_ID | int | Идентификатор веб-формы. |
| TIMESTAMP\_X | datetime | Время последнего изменения. |
| DATE\_CREATE | datetime | Время создания. |
| STATUS\_ID | int | Идентификатор текущего [статуса](/api_help/form/terms.php#status). |
| USER\_ID | int | ID пользователя, создавшего результата (автор результата). |
| USER\_AUTH | char | Флаг авторизованности автора результата в момент создания результата [Y|N]. |
| STAT\_GUEST\_ID | int | Идентификатор посетителя, создавшего результат (инициализируется модулем "Статистика" в момент создания результата). |
| STAT\_SESSION\_ID | int | Идентификатор сессии, в которой был создан результат (инициализируется модулем "Статистика" в момент создания результата). |

### Методы

| Метод | Описание | С версии |
| --- | --- | --- |
| [Add](/api_help/form/classes/cformresult/add.php) | Создает новый результат. |  |
| [Update](/api_help/form/classes/cformresult/update.php) | Обновляет результат. |  |
| [SetField](/api_help/form/classes/cformresult/setfield.php) | Для указанного результата обновляет значения [ответа](/api_help/form/terms.php#answer) на [вопрос](/api_help/form/terms.php#question) или обновляет значение [поля](/api_help/form/terms.php#field) веб-формы. |  |
| [GetList](/api_help/form/classes/cformresult/getlist.php) | Возвращает список результатов. |  |
| [GetByID](/api_help/form/classes/cformresult/getbyid.php) | Возвращает поля результата. |  |
| [GetDataByID](/api_help/form/classes/cformresult/getdatabyid.php) | Возвращает ряд массивов, содержащих данные по значениям ответов на вопросы веб-формы, а также значения полей веб-формы для указанного результата. |  |
| [GetDataByIDForHTML](/api_help/form/classes/cformresult/getdatabyidforhtml.php) | Возвращает массив значений ответов на вопросы веб-формы, а также значения полей веб-формы для указанного результата. Ключи данного массива в точности соответствуют [правилам](/api_help/form/htmlnames.php) формирования имен HTML полей для веб-формы. | 4.0.4 |
| [Reset](/api_help/form/classes/cformresult/reset.php) | Удаляет значения ответов и значения полей веб-формы для указанного результата. | 4.0.4 |
| [Delete](/api_help/form/classes/cformresult/delete.php) | Удаляет указанный результат. | 4.0.4 |
| [Mail](/api_help/form/classes/cformresult/mail.php) | Создает почтовое событие. | 4.0.4 |
| [SetEvent](/api_help/form/classes/cformresult/setevent.php) | Создает событие в модуле "Статистика". | 4.0.4 |
| [SetStatus](/api_help/form/classes/cformresult/setstatus.php) | Устанавливает указанный статус для указанного результата. | 4.0.4 |
| [GetCount](/api_help/form/classes/cformresult/getcount.php) | Возвращает количество результатов указанной веб-формы. | 4.0.4 |
| [GetPermissions](/api_help/form/classes/cformresult/getpermissions.php) | Возвращает массив [прав на результат](/api_help/form/permissions.php#result) в зависимости от его статуса. |  |

Новинки документации в соцсетях:
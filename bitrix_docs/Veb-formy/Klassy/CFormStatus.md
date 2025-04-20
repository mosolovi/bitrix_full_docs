[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormStatus](/api_help/form/classes/cformstatus/index.php)

Класс CFormStatus (4.0.4)

Класс CFormStatus
=================

Включить вкладки

Поля

Методы

**CFormStatus** - класс для работы со [статусами](/api_help/form/terms.php#status).

### Поля

| Поле | Тип | Описание |
| --- | --- | --- |
| ID | int | Идентификатор [статуса](/api_help/form/terms.php#status). |
| FORM\_ID | int | Идентификатор [веб-формы](/api_help/form/terms.php#form). |
| TIMESTAMP\_X | datetime | Время последнего изменения параметров [статуса](/api_help/form/terms.php#status). |
| ACTIVE | char | Флаг активности [статуса](/api_help/form/terms.php#status) [Y|N]. |
| C\_SORT | int | Индекс сортировки [статуса](/api_help/form/terms.php#status). |
| TITLE | varchar(255) | Заголовок [статуса](/api_help/form/terms.php#status). |
| DESCRIPTION | varchar(2000) | Описание [статуса](/api_help/form/terms.php#status). |
| DEFAULT\_VALUE | char | Флаг установки у [результата](/api_help/form/terms.php#result) данного [статуса](/api_help/form/terms.php#status) по умолчанию [Y|N]. |
| CSS | varchar(255) | Имя CSS класса для вывода заголовка [статуса](/api_help/form/terms.php#status). |
| HANDLER\_OUT | varchar(255) | Путь относительно корня к [обработчику](/api_help/form/status_processing.php), вызываемому при смене у [результата](/api_help/form/terms.php#result) данного [статуса](/api_help/form/terms.php#status) на другой. |
| HANDLER\_IN | varchar(255) | Путь относительно корня к [обработчику](/api_help/form/status_processing.php), вызываемому при смене у [результата](/api_help/form/terms.php#result) какого-либо [статуса](/api_help/form/terms.php#status) на данный. |

### Методы

| Метод | Описание | С версии |
| --- | --- | --- |
| [Set](/api_help/form/classes/cformstatus/set.php) | Добавляет новый [статус](/api_help/form/terms.php#status) либо обновляет параметры существующего. |  |
| [GetList](/api_help/form/classes/cformstatus/getlist.php) | Возвращает список [статусов](/api_help/form/terms.php#status) указанной [веб-формы](/api_help/form/terms.php#form). |  |
| [GetByID](/api_help/form/classes/cformstatus/getbyid.php) | Возвращает параметры [статуса](/api_help/form/terms.php#status). |  |
| [Copy](/api_help/form/classes/cformstatus/copy.php) | Копирует [статус](/api_help/form/terms.php#status). |  |
| [Delete](/api_help/form/classes/cformstatus/delete.php) | Удаляет [статус](/api_help/form/terms.php#status). |  |
| [GetPermissions](/api_help/form/classes/cformstatus/getpermissions.php) | Возвращает массив прав текущего пользователя для указанного [статуса](/api_help/form/terms.php#status). |  |
| [GetPermissionList](/api_help/form/classes/cformstatus/getpermissionlist.php) | Возвращает массивы групп пользователей с определёнными [правами](/api_help/form/permissions.php#result) для указанного [статуса](/api_help/form/terms.php#status). |  |
| [GetDropdown](/api_help/form/classes/cformstatus/getdropdown.php) | Возвращает список [статусов](/api_help/form/terms.php#status) в формате для [вывода выпадающего списка](/api_help/main/functions/html/selectbox.php) одиночного выбора. |  |

Новинки документации в соцсетях:
[Веб-формы](/api_help/form/index.php)

[События](/api_help/form/events/index.php)

События веб-форм

События веб-форм
================

Все события вызываются **перед** соответствующим вызовом
файлов-обработчиков статуса результата. Возврат обработчиком каких-либо значений
не предполагается. Те обработчики, для которых это указано (onBefore\*), могут
возвращать какие-либо сообщения посредством генерации системного исключения
(CMain::ThrowException()). В случае появления такого исключения все последующие
операции с результатом прерываются (включая обработчики статусов веб-формы). При
этом все равно вызываются все обработчики текущего события. Данные, передаваемые
по ссылкам, допускают непосредственное изменение значений.

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| OnAfterFormCrmAdd | после добавления сервера CRM, с которым можно связать форму. | CFormCrm::Add | 11.5.0 |
| OnAfterFormCrmDelete | после удаления сервера CRM, с которым может быть связана форма. | CFormCrm::Delete | 11.5.0 |
| OnAfterFormCrmUpdate | после обновления сервера CRM, с которым может быть связана форма. | CFormCrm::Update | 11.5.0 |
| OnBeforeFormCrmAdd | перед добавлением сервера CRM, с которым может быть связана форма. | CFormCrm::Add | 11.5.0 |
| OnBeforeFormCrmDelete | перед удалением сервера CRM, с которым может быть связана форма. | CFormCrm::Delete | 11.5.0 |
| OnBeforeFormCrmUpdate | перед обновлением сервера CRM, с которым может быть связана форма. | CFormCrm::Update | 11.5.0 |
| [onBeforeResultAdd](onbeforeresultadd.php) | перед добавлением нового результата веб-формы. | [CFormResult::Add](/api_help/form/classes/cformresult/add.php) | 6.5.2 |
| [onAfterResultAdd](onafterresultadd.php) | после добавления нового результата веб-формы. | [CFormResult::Add](/api_help/form/classes/cformresult/add.php) | 6.5.2 |
| [onBeforeResultUpdate](onbeforeresultupdate.php) | перед сохранением изменений существующего результата. | [CFormResult::Update](/api_help/form/classes/cformresult/update.php) | 6.5.2 |
| [onAfterResultUpdate](onafterresultupdate.php) | после сохранения изменений результата веб-формы. | [CFormResult::Update](/api_help/form/classes/cformresult/update.php) | 6.5.2 |
| [onBeforeResultDelete](onbeforeresultdelete.php) | перед удалением результата веб-формы. | [CFormResult::Delete](/api_help/form/classes/cformresult/delete.php) | 6.5.2 |
| [onBeforeResultStatusChange](onbeforeresultstatuschange.php) | перед изменением статуса результата веб-формы. | [CFormResult::SetStatus](/api_help/form/classes/cformresult/setstatus.php) | 6.5.2 |
| [onAfterResultStatusChange](onafterresultstatuschange.php) | после изменения статуса результата веб-формы. | [CFormResult::SetStatus](/api_help/form/classes/cformresult/setstatus.php) | 6.5.2 |
| onFormValidatorBuildList | при сборе списка кастомных валидаторов полей формы. | [CFormValidator::GetAllList](/api_help/form/classes/cformvalidator/getalllist.php) | 6.0.0 |

Новинки документации в соцсетях:
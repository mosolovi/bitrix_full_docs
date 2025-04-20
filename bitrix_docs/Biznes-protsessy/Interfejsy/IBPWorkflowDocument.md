[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

IBPWorkflowDocument

IBPWorkflowDocument
===================

Класс документа должен реализовывать методы интерфейса **IBPWorkflowDocument**. Этот интерфейс содержит методы, которые необходимы бизнес-процессу для работы с документом.

Для того чтобы бизнес-процесс мог работать с каким-либо объектом, необходимо выбрать, что будет являться документом, что будет являться типом документа, какие будут идентификаторы у документа и типа документа. Кроме того нужно реализовать класс документа в соответствии с интерфейсом **IBPWorkflowDocument**.

Тип документа и документ определяются своими идентификаторами, которые имеют вид кортежа из трех элементов: кода модуля, имени класса документа и некоторого кода (как правило, кода элемента). Подробнее смотрите статью [Документ](/api_help/bizproc/doc.php).

#### Методы

| Название | Описание | **С версии** |
| --- | --- | --- |
| [CanUserOperateDocument](/api_help/bizproc/interface/IBPWorkflowDocument/CanUserOperateDocument.php) | Метод проверяет права на выполнение операций над заданным документом. | 8.5 |
| [CanUserOperateDocumentType](/api_help/bizproc/interface/IBPWorkflowDocument/CanUserOperateDocumentType.php) | Метод проверяет права на выполнение операций над документами заданного типа | 8.5 |
| [CreateDocument](/api_help/bizproc/interface/IBPWorkflowDocument/CreateDocument.php) | Метод создает новый документ с указанными свойствами (полями) и возвращает его код. | 8.5 |
| [DeleteDocument](/api_help/bizproc/interface/IBPWorkflowDocument/DeleteDocument.php) | Метод удаляет указанный документ. | 8.5 |
| [GetAllowableOperations](/api_help/bizproc/interface/IBPWorkflowDocument/GetAllowableOperations.php) | Метод для типа документа возвращает массив доступных операций. | 8.5 |
| [GetAllowableUserGroups](/api_help/bizproc/interface/IBPWorkflowDocument/GetAllowableUserGroups.php) | Метод для типа документа возвращает массив возможных групп пользователей. | 8.5 |
| [GetDocument](/api_help/bizproc/interface/IBPWorkflowDocument/GetDocument.php) | Метод возвращает свойства (поля) документа в виде ассоциативного массива. | 8.5 |
| [GetDocumentAdminPage](/api_help/bizproc/interface/IBPWorkflowDocument/GetDocumentAdminPage.php) | Метод по коду документа возвращает ссылку на страницу документа в административной части. | 8.5 |
| [GetDocumentFields](/api_help/bizproc/interface/IBPWorkflowDocument/GetDocumentFields.php) | Метод возвращает массив свойств (полей), которые имеет документ данного типа. | 8.5 |
| [GetDocumentForHistory](/api_help/bizproc/interface/IBPWorkflowDocument/GetDocumentForHistory.php) | Метод возвращает массив произвольной структуры, содержащий всю информацию о документе. | 8.5 |
| [GetUsersFromUserGroup](/api_help/bizproc/interface/IBPWorkflowDocument/GetUsersFromUserGroup.php) | Метод возвращает пользователей указанной группы для указанного документа в виде массива кодов пользователей. | 8.5 |
| [IsDocumentLocked](/api_help/bizproc/interface/IBPWorkflowDocument/IsDocumentLocked.php) | Метод проверяет, заблокирован ли указанный документ для указанного бизнес-процесса. | 8.5 |
| [LockDocument](/api_help/bizproc/interface/IBPWorkflowDocument/LockDocument.php) | Метод блокирует указанный документ для указанного бизнес-процесса. | 8.5 |
| [PublishDocument](/api_help/bizproc/interface/IBPWorkflowDocument/PublishDocument.php) | Метод публикует документ, то есть делает его доступным в публичной части сайта. | 8.5 |
| [RecoverDocumentFromHistory](/api_help/bizproc/interface/IBPWorkflowDocument/RecoverDocumentFromHistory.php) | Метод восстанавливает указанный документ из массива. | 8.5 |
| [UnlockDocument](/api_help/bizproc/interface/IBPWorkflowDocument/UnlockDocument.php) | Метод разблокирует указанный документ. | 8.5 |
| [UnpublishDocument](/api_help/bizproc/interface/IBPWorkflowDocument/UnpublishDocument.php) | Метод снимает документ с публикации, то есть делает его недоступным в публичной части сайта. | 8.5 |
| [UpdateDocument](/api_help/bizproc/interface/IBPWorkflowDocument/UpdateDocument.php) | Метод изменяет свойства (поля) указанного документа на указанные значения. | 8.5 |

Новинки документации в соцсетях:
[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

CBPDocument (С версии 8.5.1)

CBPDocument
===========

**CBPDocument** - вспомогательный класс, содержащий статические методы-обертки для удобного использования API модуля бизнес-процессов.

Например, для того, чтобы запустить бизнес-процесс по коду его шаблона, можно использовать код:

```
$runtime = CBPRuntime::GetRuntime();
$wi = $runtime->CreateWorkflow($workflowTemplateId, $documentId, $arParameters);
$wi->Start(); Копировать
```

Или можно использовать метод:

```
string CBPDocument::StartWorkflow($workflowTemplateId, $documentId, $arParameters, &$arErrors)Копировать
```

который кроме того обработает исключения, собрав их в массив **$arErrors**, и вернет идентификатор бизнес-процесса.

#### Методы класса

| Метод | Описание | **С версии** |
| --- | --- | --- |
| [AddDocumentToHistory](/api_help/bizproc/bizproc_classes/CBPDocument/AddDocumentToHistory.php) | Метод добавляет текущую версию документа в историю. | 9.0.0 |
| [AutoStartWorkflows](/api_help/bizproc/bizproc_classes/CBPDocument/AutoStartWorkflows.php) | Метод запускает рабочие потоки, настроенные на автозапуск. |  |
| [CanOperate](/api_help/bizproc/bizproc_classes/CBPDocument/CanOperate.php) | Метод проверяет, может ли указанный пользователь совершить указанную операцию, если документ находится в указанных состояниях. |  |
| [CanUserOperateDocument](/api_help/bizproc/bizproc_classes/CBPDocument/CanUserOperateDocument.php) | Метод проверяет путем обращения к сущности документа, может ли пользователь совершать указанную операцию с документом. |  |
| [CanUserOperateDocumentType](/api_help/bizproc/bizproc_classes/CBPDocument/CanUserOperateDocumentType.php) | Метод проверяет путем обращения к сущности типа документа, может ли пользователь совершать указанную операцию с документами данного типа. |  |
| [DeleteWorkflowTemplate](/api_help/bizproc/bizproc_classes/CBPDocument/DeleteWorkflowTemplate.php) | Метод удаляет шаблон бизнес-процесса. |  |
| [GetAllowableEvents](/api_help/bizproc/bizproc_classes/CBPDocument/GetAllowableEvents.php) | Метод возвращает массив событий, которые указанный пользователь может отправить рабочему потоку в указанном состоянии. |  |
| [GetAllowableOperations](/api_help/bizproc/bizproc_classes/CBPDocument/GetAllowableOperations.php) | Метод возвращает массив операций, которые указанный пользователь может совершить, если документ находится в указанных состояниях. |  |
| [GetDocumentState](/api_help/bizproc/bizproc_classes/CBPDocument/GetDocumentState.php) | Метод для данного документа возвращает состояние указанного рабочего потока. |  |
| [GetDocumentStates](/api_help/bizproc/bizproc_classes/CBPDocument/GetDocumentStates.php) | Метод возвращает массив всех рабочих потоков и их состояний для данного документа. |  |
| [GetUserTasksForWorkflow](/api_help/bizproc/bizproc_classes/CBPDocument/GetUserTasksForWorkflow.php) | Метод возвращает массив заданий для данного пользователя в данном рабочем потоке. |  |
| [GetWorkflowTemplatesForDocumentType](/api_help/bizproc/bizproc_classes/CBPDocument/GetWorkflowTemplatesForDocumentType.php) | Метод возвращает массив шаблонов рабочих потоков для данного типа документа. |  |
| [OnDocumentDelete](/api_help/bizproc/bizproc_classes/CBPDocument/OnDocumentDelete.php) | Метод удаляет все связанные с документом записи модуля бизнес-процессов. |  |
| [SendExternalEvent](/api_help/bizproc/bizproc_classes/CBPDocument/SendExternalEvent.php) | Метод отправляет внешнее событие рабочему потоку. |  |
| [StartWorkflow](/api_help/bizproc/bizproc_classes/CBPDocument/StartWorkflow.php) | Метод запускает рабочий поток по коду его шаблона. Это рекомендуемый метод для запуска бизнес-процессов. |  |
| [TerminateWorkflow](/api_help/bizproc/bizproc_classes/CBPDocument/TerminateWorkflow.php) | Метод останавливает выполнение рабочего потока. |  |
| [UpdateWorkflowTemplate](/api_help/bizproc/bizproc_classes/CBPDocument/UpdateWorkflowTemplate.php) | Метод изменяет параметры шаблона бизнес-процесса. |  |

Новинки документации в соцсетях:
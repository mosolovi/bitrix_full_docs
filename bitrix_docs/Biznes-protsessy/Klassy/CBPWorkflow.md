[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

CBPWorkflow (С версии 8.5.6)

CBPWorkflow
===========

**CBPWorkflow** - класс экземпляра бизнес-процесса. Он управляет бизнес-процессом, умеет отправлять на запуск его действия, транслировать и обрабатывать события.

Для каждого бизнес-процесса существует свой собственный объект-оболочка.
Получить объект-оболочку можно с помощью методов **CreateWorkflow** и **GetWorkflow** исполняющей среды:

```
$runtime = CBPRuntime::GetRuntime();
$wi = $runtime->CreateWorkflow($workflowTemplateId, $documentId, $arParameters);Копировать
```

В коде действия объект-оболочка для бизнес-процесса, в который входит это действие, доступна через переменную-член workflow:

```
$this->workflow->ExecuteActivity($activity);Копировать
```

#### Методы класса

| Метод | Описание | **С версии** |
| --- | --- | --- |
| [Конструктор](/api_help/bizproc/bizproc_classes/CBPWorkflow/constructor.php) | Создает новый экземпляр класса. |  |
| [GetService](/api_help/bizproc/bizproc_classes/CBPWorkflow/GetService.php) | Возвращает сервис исполняющей среды по его имени. |  |
| [GetRuntime](/api_help/bizproc/bizproc_classes/CBPWorkflow/GetRuntime.php) | Возвращает экземпляр исполняющей среды. |  |
| [GetInstanceId](/api_help/bizproc/bizproc_classes/CBPWorkflow/GetInstanceId.php) | Возвращает идентификатор бизнес-процесса. |  |
| [GetExecutionStatus](/api_help/bizproc/bizproc_classes/CBPWorkflow/GetExecutionStatus.php) | Возвращает статус выполнения бизнес-процесса. |  |
| [GetExecutionResult](/api_help/bizproc/bizproc_classes/CBPWorkflow/GetExecutionResult.php) | Возвращает результат выполнения бизнес-процесса. |  |
| [GetDocumentId](/api_help/bizproc/bizproc_classes/CBPWorkflow/GetDocumentId.php) | Возвращает идентификатор документа, над которым запущен бизнес-процесс. |  |

Новинки документации в соцсетях:
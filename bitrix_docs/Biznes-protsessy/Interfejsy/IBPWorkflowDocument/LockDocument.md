[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

LockDocument

LockDocument
============

```
bool
IBPWorkflowDocument::LockDocument(
	mixed documentId,
	string workflowId
);Копировать
```

Метод блокирует указанный документ для указанного бизнес-процесса. Заблокированный документ может изменяться только указанным бизнес-процессом. Если удалось заблокировать документ, то возвращается true, иначе – false.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentId* | Код документа |
| *workflowId* | Код бизнес-процесса |

Новинки документации в соцсетях:
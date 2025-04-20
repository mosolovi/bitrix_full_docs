[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

UnlockDocument

UnlockDocument
==============

```
bool
IBPWorkflowDocument::UnlockDocument(
	mixed documentId,
	string workflowId
);Копировать
```

Метод разблокирует указанный документ. При разблокировке вызываются обработчики события вида "Сущность\_OnUnlockDocument", которым входящим параметром передается код документа. Если удалось разблокировать документ, то возвращается true, иначе - false.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentId* | Код документа |
| *workflowId* | Код бизнес-процесса |

Новинки документации в соцсетях:
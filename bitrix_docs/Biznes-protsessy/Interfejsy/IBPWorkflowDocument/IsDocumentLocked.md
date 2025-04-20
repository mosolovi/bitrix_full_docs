[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

IsDocumentLocked

IsDocumentLocked
================

```
bool
IBPWorkflowDocument::IsDocumentLocked(
	mixed documentId,
	string workflowId
);Копировать
```

Метод проверяет, заблокирован ли указанный документ для указанного бизнес-процесса. Т.е. если для данного бизнес-процесса документ не доступен для записи из-за того, что он заблокирован другим бизнес-процессом, то метод должен вернуть true, иначе - false.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentId* | Код документа |
| *workflowId* | Код бизнес-процесса |

Новинки документации в соцсетях:
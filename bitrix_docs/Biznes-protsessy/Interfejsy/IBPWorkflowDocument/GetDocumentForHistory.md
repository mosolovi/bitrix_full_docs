[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

GetDocumentForHistory

GetDocumentForHistory
=====================

```
array
IBPWorkflowDocument::GetDocumentForHistory(
	mixed documentId
);Копировать
```

Метод возвращает массив произвольной структуры, содержащий всю информацию о документе. По этому массиву документ восстанавливается методом [RecoverDocumentFromHistory](/api_help/bizproc/interface/IBPWorkflowDocument/RecoverDocumentFromHistory.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentId* | Код документа |

Новинки документации в соцсетях:
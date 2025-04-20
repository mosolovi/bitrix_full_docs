[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

DeleteDocument

DeleteDocument
==============

```
void
IBPWorkflowDocument::DeleteDocument(
	mixed documentId
);Копировать
```

Метод удаляет указанный документ.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentId* | Код документа |

#### Примеры использования

```
<?
public function DeleteDocument($documentId)
{
	$documentId = intval($documentId);
	if ($documentId <= 0)
		throw new CBPArgumentNullException("documentId");
	CIBlockElement::Delete($documentId);
}
?>Копировать
```

Новинки документации в соцсетях:
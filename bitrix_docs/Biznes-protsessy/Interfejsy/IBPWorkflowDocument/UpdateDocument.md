[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

UpdateDocument

UpdateDocument
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
IBPWorkflowDocument::UpdateDocument(
	mixed documentId,
	array arFields
);Копировать
```

Метод изменяет свойства (поля) указанного документа на указанные значения.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| documentId | Код документа |
| arFields | Массив новых значений свойств документа в виде  ``` array( 	код_свойства => значение, 	... )Копировать ```  Коды свойств соответствуют кодам свойств, возвращаемым методом GetDocumentFields. |

### Примеры использования

```
<?
public function UpdateDocument($documentId, $arFields)
{
	$documentId = intval($documentId);
	if ($documentId <= 0)
		throw new CBPArgumentNullException("documentId");
	$iblockElement = new CIBlockElement();
	$res = $iblockElement->Update($documentId, $arFields);
	if (!$res)
		throw new Exception($iblockElement->LAST_ERROR);
}
?>Копировать
```

Новинки документации в соцсетях:
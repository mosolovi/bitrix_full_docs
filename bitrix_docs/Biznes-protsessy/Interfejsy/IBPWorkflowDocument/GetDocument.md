[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

GetDocument

GetDocument
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
array
IBPWorkflowDocument::GetDocument(
	mixed documentId
);Копировать
```

Метод возвращает свойства (поля) документа в виде ассоциативного массива вида

```
array(
	код_свойства => значение,
	...
)Копировать
```

Определены все свойства, которые возвращает метод [GetDocumentFields](/api_help/bizproc/interface/IBPWorkflowDocument/GetDocumentFields.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentId* | Идентификатор документа |

### Примеры использования

```
<?
public function GetDocument($documentId)
{
	$documentId = intval($documentId);
	if ($documentId <= 0)
		throw new CBPArgumentNullException("documentId");
	$arResult = null;
	$dbDocumentList = CIBlockElement::GetList(
		array(),
		array("ID" => $documentId, "SHOW_NEW"=>"Y", "SHOW_HISTORY" => "Y")
	);
	if ($objDocument = $dbDocumentList->GetNextElement())
	{
		$arDocumentFields = $objDocument->GetFields();
		$arDocumentProperties = $objDocument->GetProperties();
		foreach ($arDocumentFields as $fieldKey => $fieldValue)
		{
			if (substr($fieldKey, 0, 1) != "~")
				$arResult[$fieldKey] = $fieldValue;
		}
		foreach ($arDocumentProperties as $propertyKey => $propertyValue)
			$arResult["PROPERTY_".$propertyKey] = $propertyValue["VALUE"];
	}
	return $arResult;
}
?>Копировать
```

Новинки документации в соцсетях:
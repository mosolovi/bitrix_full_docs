[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

GetDocumentFields

GetDocumentFields
=================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
array
IBPWorkflowDocument::GetDocumentFields(
	mixed documentType
);Копировать
```

Метод возвращает массив свойств (полей), которые имеет документ данного типа. Метод [GetDocument](/api_help/bizproc/interface/IBPWorkflowDocument/GetDocument.php) возвращает значения свойств для заданного документа. Возвращаемый массив имеет вид

```
array(
	код_свойства => array(
		"NAME" => название_свойства,
		"TYPE" => тип_свойства
	), 
	...
)Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentType* | Идентификатор типа документа |

### Примеры использования

```
<?
public function GetDocumentFields($documentType)
{
	$iblockId = intval(substr($documentType, strlen("iblock_")));
	if ($iblockId <= 0)
		throw new CBPArgumentOutOfRangeException("documentType", $documentType);
	$arResult = array(
		"ID" => array(
			"Name" => GetMessage("IBD_FIELD_ID"),
			"Type" => "int",
			"Filterable" => true,
			"Editable" => false,
			"Required" => false,
			"Multiple" => false,
		),
		"TIMESTAMP_X" => array(
			"Name" => GetMessage("IBD_FIELD_TIMESTAMP_X"),
			"Type" => "datetime",
			"Filterable" => true,
			"Editable" => true,
			"Required" => false,
			"Multiple" => false,
		),
		...
	);
	return $arResult;
}
?>Копировать
```

Новинки документации в соцсетях:
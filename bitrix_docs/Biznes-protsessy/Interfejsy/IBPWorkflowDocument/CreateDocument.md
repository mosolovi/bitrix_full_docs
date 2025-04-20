[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

CreateDocument

CreateDocument
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
mixed
IBPWorkflowDocument::CreateDocument(
	mixed pid,
	array arFields
);Копировать
```

Метод создает новый документ с указанными свойствами (полями) и возвращает его код.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *pid* | Не используется |
| *arFields* | Массив значений свойств документа в виде  ``` array( 	код_свойства => значение, 	... )Копировать ```  Коды свойств соответствуют кодам свойств, возвращаемым методом [GetDocumentFields](/api_help/bizproc/interface/IBPWorkflowDocument/GetDocumentFields.php). |

### Примеры использования

```
<?
public function CreateDocument($pid, $arFields)
{
	$iblockElement = new CIBlockElement();
	$id = $iblockElement->Add($arFields);
	if (!$id || $id <= 0)
		throw new Exception($iblockElement->LAST_ERROR);
	return $id;
}
?>Копировать
```

Новинки документации в соцсетях:
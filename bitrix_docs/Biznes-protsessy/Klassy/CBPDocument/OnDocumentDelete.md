[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

OnDocumentDelete

OnDocumentDelete
================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
public static function CBPDocument::OnDocumentDelete(
	array documentId,
	array &arErrors
);Копировать
```

Метод удаляет все связанные с документом записи модуля бизнес-процессов.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentId* | Код документа в виде массива *array(модуль, класс\_документа, код\_документа\_в\_модуле)* |
| *arErrors* | Массив ошибок, которые произошли при удалении в виде  ``` array(    array(       "code" => код_ошибки,       "message" => сообщение,       "file" => путь_к_файлу    ),    ... )Копировать ``` |

### Примеры использования

```
<?
$arState = CBPStateService::GetWorkflowState($deleteWorkflowId);
if (count($arState) > 0)
{
	$arErrorsTmp = array();
	CBPDocument::OnDocumentDelete($arState["DOCUMENT_ID"], $arErrorsTmp);
	if (count($arErrorsTmp) > 0)
	{
		foreach ($arErrorsTmp as $e)
			$errorMessage .= $e["message"].". ";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
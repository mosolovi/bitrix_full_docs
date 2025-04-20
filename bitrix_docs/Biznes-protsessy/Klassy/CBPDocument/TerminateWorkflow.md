[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

TerminateWorkflow

TerminateWorkflow
=================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
public static function CBPDocument::TerminateWorkflow(
	string workflowId,
	array documentId,
	array &arErrors
);Копировать
```

Метод останавливает выполнение рабочего потока.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *workflowId* | Код рабочего потока |
| *documentId* | Код документа в виде массива *array(модуль, класс\_документа, код\_документа\_в\_модуле)* |
| *arErrors* | Массив ошибок, которые произошли при остановке рабочего потока в виде  ``` array( 	array( 		"code" => код_ошибки, 		"message" => сообщение, 		"file" => путь_к_файлу 	), 	... )Копировать ``` |

### Примеры использования

```
<?
$arState = CBPStateService::GetWorkflowState($stopWorkflowId);
if (count($arState) > 0)
{
	CBPDocument::TerminateWorkflow(
		$stopWorkflowId,
		$arState["DOCUMENT_ID"],
		$arErrorsTmp
	);
	if (count($arErrorsTmp) > 0)
	{
		foreach ($arErrorsTmp as $e)
			$errorMessage .= $e["message"].". ";
	}
}
?>Копировать
```

Новинки документации в соцсетях:
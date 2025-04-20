[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

GetUserTasksForWorkflow

GetUserTasksForWorkflow
=======================

Включить вкладки

Описание и параметры

Возвращаемое значение

Примеры использования

### Описание и параметры

```
array
public static function CBPDocument::GetUserTasksForWorkflow(
	integer userId,
	string workflowId
);Копировать
```

Метод возвращает массив заданий для данного пользователя в данном рабочем потоке.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *userId* | Код пользователя |
| *workflowId* | Код бизнес-процесса |

### Возвращаемое значение

Возвращаемый массив имеет вид:

```
array(
	array(
		"ID" => код_задания,
		"NAME" => название_задания,
		"DESCRIPTION" => описание_задания,
	),
	. . .
)Копировать
```

### Примеры использования

```
<?
$documentType = array("bizproc", "CBPVirtualDocument", "type_".$iblockId);
$documentId = array("bizproc", "CBPVirtualDocument", $id);
$arDocumentStates = CBPDocument::GetDocumentStates($documentType, $documentId);
foreach ($arDocumentStates as $arDocumentState)
{
	$ar = CBPDocument::GetUserTasksForWorkflow($GLOBALS["USER"]->GetID(), $arDocumentState["ID"]);
	print_r($ar);
}
?>Копировать
```

Новинки документации в соцсетях:
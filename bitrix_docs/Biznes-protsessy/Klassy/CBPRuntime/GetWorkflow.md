[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPRuntime](/api_help/bizproc/bizproc_classes/CBPRuntime/index.php)

GetWorkflow

GetWorkflow
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CBPWorkflow
public function CBPRuntime::GetWorkflow(
	string workflowId
);Копировать
```

Метод возвращает экземпляр бизнес-процесса по его идентификатору.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *workflowId* | Идентификатор бизнес-процесса |

#### Возвращаемое значение

Возвращается экземпляр класса [CBPWorkflow](/api_help/bizproc/bizproc_classes/CBPWorkflow/index.php), представляющий собой экземпляр существующего бизнес-процесса.

#### Исключения

| Код | Описание |
| --- | --- |
| *workflowId* | Не указан код бизнес-процесса |
| *Empty root activity* | Не удалось восстановить экземпляр бизнес-процесса |

### Примеры использования

```
<?
// Получим код документа, над которым запущен бизнес-процесс с указанным идентификатором
$runtime = CBPRuntime::GetRuntime();
try
{
	$workflow = $runtime->GetWorkflow($workflowId);
	$d = $workflow->GetDocumentId();
}
catch(Exception $e)
{
	//
}
?>Копировать
```

Новинки документации в соцсетях:
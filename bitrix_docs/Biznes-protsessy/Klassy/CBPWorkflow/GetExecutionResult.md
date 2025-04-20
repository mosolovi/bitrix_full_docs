[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPWorkflow](/api_help/bizproc/bizproc_classes/CBPWorkflow/index.php)

GetExecutionResult

GetExecutionResult
==================

```
int
private function CBPWorkflow::GetExecutionResult();Копировать
```

Метод возвращает результат выполнения бизнес-процесса.

#### Возвращаемое значение

Возвращаемое значение соответствует константам класса **CBPActivityExecutionResult**. Возможные значения:

* **CBPActivityExecutionResult::None** - результат выполнения бизнес-процесса не установлен,
* **CBPActivityExecutionResult::Succeeded** - бизнес-процесс завершен успешно,
* **CBPActivityExecutionResult::Canceled** - бизнес-процесс отменен,
* **CBPActivityExecutionResult::Faulted** - бизнес-процесс остановлен по ошибке,
* **CBPActivityExecutionResult::Uninitialized** - бизнес-процесс не инициализирован.

#### Примеры использования

```
<?
$runtime = CBPWorkflow::GetRuntime();
try
{
	$workflow = $runtime->GetWorkflow($workflowId);
}
catch (Exception $e)
{
	//
}
$executionResult = $workflow->GetExecutionResult();
switch ($executionResult)
{
	case CBPActivityExecutionResult::None:
		echo "Нет";
		break;
	case CBPActivityExecutionResult::Succeeded:
		echo "Успешно";
		break;
	case CBPActivityExecutionResult::Canceled:
		echo "Отменено";
		break;
	case CBPActivityExecutionResult::Faulted:
		echo "Ошибка";
		break;
	case CBPActivityExecutionResult::Uninitialized:
		echo "Не инициализировано";
		break;
	default:
		echo "Не определено";
}
?>Копировать
```

Новинки документации в соцсетях:
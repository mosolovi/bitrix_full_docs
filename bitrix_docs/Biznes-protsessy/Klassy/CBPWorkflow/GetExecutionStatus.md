[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPWorkflow](/api_help/bizproc/bizproc_classes/CBPWorkflow/index.php)

GetExecutionStatus

GetExecutionStatus
==================

```
int
private function CBPWorkflow::GetExecutionStatus();Копировать
```

Метод возвращает текущий статус выполнения бизнес-процесса.

#### Возвращаемое значение

Возвращаемое значение соответствует константам класса **CBPActivityExecutionStatus**. Возможные значения:

* **CBPActivityExecutionStatus::Initialized** - бизнес-процесс создан,
* **CBPActivityExecutionStatus::Executing** - бизнес-процесс выполняется,
* **CBPActivityExecutionStatus::Canceling** - бизнес-процесс отменен,
* **CBPActivityExecutionStatus::Closed** - бизнес-процесс завершен,
* **CBPActivityExecutionStatus::Faulting** - бизнес-процесс остановлен по ошибке.

Новинки документации в соцсетях:
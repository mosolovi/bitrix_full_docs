[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPActivity](/api_help/bizproc/bizproc_classes/CBPActivity/index.php)

AddStatusChangeHandler

AddStatusChangeHandler
======================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CBPActivity::AddStatusChangeHandler(
	int event,
	IBPActivityEventListener eventHandler
);Копировать
```

Метод добавляет новый обработчик события изменения статуса действия.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *event* | Одна из констант **CBPActivity::ExecutingEvent**, **CBPActivity::ClosedEvent**, **CBPActivity::FaultingEvent**, определяющая, на какое изменение статуса будет вызываться обработчик. |
| *eventHandler* | Обработчик события, который реализует интерфейс **IBPActivityEventListener**. |

#### Смотрите также

* [RemoveStatusChangeHandler](/api_help/bizproc/bizproc_classes/CBPActivity/RemoveStatusChangeHandler.php)

### Примеры использования

```
<?
class CBPMyActivity
	extends CBPCompositeActivity    // наследуем, так как составное действие
	implements IBPEventActivity	// обработка события завершения дочернего действия
{
	// Исполняемый метод действия
	public function Execute()
	{
		// Возьмем первое дочернее действие
		$activity = $this->arActivities[0];
		// Подпишемся на событие изменения статуса дочернего действия (завершение)
		$activity->AddStatusChangeHandler(self::ClosedEvent, $this);
		// Отправим дочернее действие исполняющей среде на выполнение
		$this->workflow->ExecuteActivity($activity);
		// Вернем указание исполняющей среде, что действие еще выполняется
		return CBPActivityExecutionStatus::Executing;
	}
	// Обработчик события изменения статуса интерфейса IBPEventActivity
	// Параметром передается действие, изменившее статус
	protected function OnEvent(CBPActivity $sender)
	{
		// Отпишемся от события изменения статуса дочернего действия (завершения)
		$sender->RemoveStatusChangeHandler(self::ClosedEvent, $this);
		// Дочернее действие завершено, выполняем другой необходимый нам код
		// Например завершаем действие
		$this->workflow->CloseActivity($this);
	}
}
?>Копировать
```

Новинки документации в соцсетях:
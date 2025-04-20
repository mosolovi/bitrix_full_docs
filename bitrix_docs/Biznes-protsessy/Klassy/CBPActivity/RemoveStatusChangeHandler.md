[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPActivity](/api_help/bizproc/bizproc_classes/CBPActivity/index.php)

RemoveStatusChangeHandler

RemoveStatusChangeHandler
=========================

```
void
CBPActivity::RemoveStatusChangeHandler(
	int event,
	IBPActivityEventListener eventHandler
);Копировать
```

Метод удаляет обработчик события изменения статуса действия.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *event* | Одна из констант **CBPActivity::ExecutingEvent**, **CBPActivity::ClosedEvent**, **CBPActivity::FaultingEvent**, определяющая, на какое изменение статуса будет вызываться обработчик. |
| *eventHandler* | Обработчик события, который реализует интерфейс **IBPActivityEventListener**. |

#### Смотрите также

* [AddStatusChangeHandler](/api_help/bizproc/bizproc_classes/CBPActivity/AddStatusChangeHandler.php)

Новинки документации в соцсетях:
[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPActivity](/api_help/bizproc/bizproc_classes/CBPActivity/index.php)

WriteToTrackingService

WriteToTrackingService
======================

```
void
CBPActivity::WriteToTrackingService(
	string message,
	int modifiedBy = 0
	int trackingType = -1
);Копировать
```

Метод записывает произвольное сообщение в лог Бизнес-процесса. Кроме того может быть записано, от имени какого пользователя отправляется это сообщение.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *message* | Сообщение |  |
| *modifiedBy* | Идентификатор пользователя, от имени которого отправляется сообщение | 8.5.4 |
| *trackingType* | Тип записи. Указывается с помощью констант класса **CBPTrackingType**:  ``` const Unknown = 0; const ExecuteActivity = 1; const CloseActivity = 2; const CancelActivity = 3; const FaultActivity = 4; const Custom = 5; const Report = 6;Копировать ``` | 11.0.4 |

Новинки документации в соцсетях:
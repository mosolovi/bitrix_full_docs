[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPRuntime](/api_help/bizproc/bizproc_classes/CBPRuntime/index.php)

GetService

GetService
==========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CBPRuntimeService
public function GetService($name)(
	string name
);Копировать
```

Метод возвращает экземпляр сервиса исполняющей среды по его имени.

**Примечание**: доступны следующие сервисы исполняющей среды.

| Название | Класс | Описание |
| --- | --- | --- |
| SchedulerService | CBPSchedulerService | Служит для установки агента, который выполнится через указанное время и отправит внешнее событие указанному бизнес-процессу |
| StateService | CBPStateService | Служит для работы с сохраненным в базе данных состоянием бизнес-процесса |
| TrackingService | CBPTrackingService | Служит для записи сообщений в лог |
| TaskService | CBPTaskService | Служит для работы с заданиями |
| HistoryService | CBPHistoryService | Служит для работы с историей изменения документа |
| DocumentService | CBPDocumentService | Служит для работы с документом |

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *name* | Название сервиса |

#### Возвращаемое значение

Возвращается класс сервиса, наследованный от **CBPRuntimeService**.

### Примеры использования

```
<?
// Сохраним историю документа $documentId от имени пользователя $userId
$runtime = CBPRuntime::GetRuntime();
$historyService = $runtime->GetService("HistoryService");
$documentService = $runtime->GetService("DocumentService");
$historyIndex = $historyService->AddHistory(
	array(
		"DOCUMENT_ID" => $documentId,
		"NAME" => "New",
		"DOCUMENT" => null,
		"USER_ID" => $userId,
	)
);
$arDocument = $documentService->GetDocumentForHistory($documentId, $historyIndex);
if (is_array($arDocument))
{
	$historyService->UpdateHistory(
		$historyIndex,
		array(
			"NAME" => $arDocument["NAME"],
			"DOCUMENT" => $arDocument,
		)
	);
}
?>Копировать
```

Новинки документации в соцсетях:
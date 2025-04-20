[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPRuntime](/api_help/bizproc/bizproc_classes/CBPRuntime/index.php)

SendExternalEvent

SendExternalEvent
=================

```
void
public static function SendExternalEvent(
	string workflowId,
	string eventName,
	array arEventParameters = array()
);Копировать
```

Статический метод отправляет внешнее событие указанному бизнес-процессу.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *workflowId* | Идентификатор бизнес-процесса |
| *eventName* | Название события |
| *arEventParameters* | Параметры события |

#### Примеры использования

```
<?
CBPRuntime::SendExternalEvent($workflowId, $eventName, $arEventParameters);
?>Копировать
```

Новинки документации в соцсетях:
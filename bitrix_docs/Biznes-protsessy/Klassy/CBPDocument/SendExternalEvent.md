[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

SendExternalEvent

SendExternalEvent
=================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
void
public function CBPDocument::SendExternalEvent(
	string workflowId,
	string workflowEvent,
	array arParameters,
	array &arErrors
);Копировать
```

Метод отправляет внешнее событие рабочему потоку.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *workflowId* | Код рабочего потока |
| *workflowEvent* | Название события |
| *arParameters* | Параметры события |
| *arErrors* | Массив ошибок, которые произошли при отправке события в виде  ``` array( 	array( 		"code" => код_ошибки, 		"message" => сообщение, 		"file" => путь_к_файлу 	), 	... )Копировать ``` |

### Смотрите также

* [CBPRuntime::SendExternalEvent](/api_help/bizproc/bizproc_classes/CBPRuntime/SendExternalEvent.php)

### Примеры использования

```
<?
$arCurrentUserGroups = $GLOBALS["USER"]->GetUserGroupArray();
if ($GLOBALS["USER"]->GetID() == $createdBy)
	$arCurrentUserGroups[] = "Author";
$arErrorTmp = array();
CBPDocument::SendExternalEvent(
	$bizprocId,
	$bizprocEvent,
	array("Groups" => $arCurrentUserGroups, "User" => $GLOBALS["USER"]->GetID()),
	$arErrorTmp
);
if (count($arErrorsTmp) > 0)
{
	foreach ($arErrorsTmp as $e)
		$fatalErrorMessage .= $e["message"].". ";
}
?>Копировать
```

Новинки документации в соцсетях:
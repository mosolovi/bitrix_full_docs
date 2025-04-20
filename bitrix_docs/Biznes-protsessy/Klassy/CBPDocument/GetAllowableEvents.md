[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

GetAllowableEvents

GetAllowableEvents
==================

Включить вкладки

Описание и параметры

Возвращаемое значение

Примеры использования

### Описание и параметры

```
array
public static function CBPDocument::GetAllowableEvents(
	int userId,
	array arGroups,
	array arState
);Копировать
```

Метод возвращает массив событий, которые указанный пользователь может отправить рабочему потоку в указанном состоянии.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *userId* | Код пользователя |
| *arGroups* | Массив групп пользователя |
| *arState* | Состояние рабочего потока |

### Возвращаемое значение

Возвращается массив событий вида

```
array(
	array(
		"NAME" => событие,
		"TITLE" => название_события
	),
	...
)Копировать
```

### Примеры использования

```
<?
$documentType = array("bizproc", "CBPVirtualDocument", "type_".$blockId);
$documentId = array("bizproc", "CBPVirtualDocument", $id);
$arCurrentUserGroups = $GLOBALS["USER"]->GetUserGroupArray();
if ($GLOBALS["USER"]->GetID() == $authorId)
	$arCurrentUserGroups[] = "Author";
$arDocumentStates = CBPDocument::GetDocumentStates($documentType, $documentId);
foreach ($arDocumentStates as $arDocumentState)
{
	$arDocumentStateEvents = CBPDocument::GetAllowableEvents($GLOBALS["USER"]->GetID(), $arCurrentUserGroups, $arDocumentState);
	print_r($arDocumentStateEvents);
}
?>Копировать
```

Новинки документации в соцсетях:
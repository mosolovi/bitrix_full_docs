[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumTopic](/api_help/forum/developer/cforumtopic/index.php)

MoveTopic2Forum (доступно с 3.3.3)

MoveTopic2Forum
===============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CForumTopic::MoveTopic2Forum(
	int TID,
	int FID
);Копировать
```

Функция переносит тему с кодом **TID** в форум с кодом **FID**. Метод статический.

**Примечание**. Метод использует внутреннюю транзакцию. Если у вас используется **MySQL** и **InnoDB**, и ранее была открыта транзакция, то ее необходимо закрыть до подключения метода.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| TID | Код темы, которую необходимо перенести. |
| FID | Код форума, в который необходимо перенести тему. |

#### Возвращаемые значения

Функция возвращает True в случае успешного переноса и False - в противном случае

### Примеры использования

```
<?
// Если тема не переносится в другой форум, значит есть какие-либо ошибки, которые можно найти: 
$strErrorMessage = "";
if (CForumTopic::MoveTopic2Forum($topics, $arParams["newFID"], $_REQUEST["leaveLink"])):
	print_r("Good!");
elseif ($GLOBALS['APPLICATION']->GetException()):
	$err = $GLOBALS['APPLICATION']->GetException();
	$strErrorMessage = $err->GetString();
	ShowError($strErrorMessage);
endif;
?>Копировать
```

Новинки документации в соцсетях:
[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagment](/api_help/ideamanagment/reference/cideamanagment/index.php)

Notification (доступен с 11.5.0)

Notification
============

```
function
CIdeaManagment::Notification(
	$arNotification = array()
);Копировать
```

Возвращает базовый объект для работы уведомлениями на идеи\комментарии. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arNotification | Массив параметров объекта менеджера идей. |

#### Возвращаемое значение

Базовый объект менеджера идей для работы с уведомлениями (*CIdeaManagmentNotify*).

#### Примеры использования

```
$arNotifyFields = array_merge(
	$arFields, 
	array(
		"TYPE"=>'IDEA_COMMENT', 
		"ACTION" => 'ADD', 
		"ID" => $commentID,
		"AUTHOR" => $AuthorName,
		"FULL_PATH" => "http://".$serverName.$commentUrl,
		"IDEA_COMMENT_TEXT" => $IdeaParser->convert4mail($arFields["POST_TEXT"]),
		"IDEA_TITLE" => $arPost['~TITLE']
	)
);
$notify = CIdeaManagment::getInstance()->Notification($arNotifyFields); Копировать
```

Новинки документации в соцсетях:
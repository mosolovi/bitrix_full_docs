[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagment](/api_help/ideamanagment/reference/cideamanagment/index.php)

IdeaComment (доступен с 11.5.0)

IdeaComment
===========

```
function
CIdeaManagment::IdeaComment(
	$CommentId = false
);Копировать
```

Возвращает объект для работы с конкретным комментарием идеи указанной во входном параметре. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| CommentId | ID комментария |

#### Возвращаемое значение

Объект менеджера идей для работы с комментарием идеи (*CIdeaManagmentIdeaComment*).

#### Примеры использования

```
$IdeaComment = CIdeaManagment::getInstance()->IdeaComment(1);Копировать
```

Новинки документации в соцсетях:
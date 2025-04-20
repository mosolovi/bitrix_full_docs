[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagmentIdeaComment](/api_help/ideamanagment/reference/cideamanagmentideacomment/index.php)

SetID (доступен с 11.5.0)

SetID
=====

```
function
CIdeaManagmentIdeaComment::SetID(
	$CommentId
);Копировать
```

Устанавливает ID комментария идеи для последующих операций с ним. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| CommentId | ID комментария. |

#### Возвращаемое значение

Возвращает текущий объект.

#### Примеры использования

```
$IdeaComment = CIdeaManagment::getInstance()->IdeaComment()->SetID(1);Копировать
```

Новинки документации в соцсетях:
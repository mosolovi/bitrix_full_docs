[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagmentIdea](/api_help/ideamanagment/reference/cideamanagmentidea/index.php)

SetID (доступен с 11.5.0)

SetID
=====

```
function
CIdeaManagmentIdea::SetID(
	IdeaId
);Копировать
```

Устанавливает ID идеи для последующих операций с ней. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| IdeaId | ID идеи |

#### Возвращаемое значение

Возвращает текущий объект.

#### Примеры использования

```
$Idea = CIdeaManagment::getInstance()->Idea()->SetID(1);Копировать
```

Новинки документации в соцсетях:
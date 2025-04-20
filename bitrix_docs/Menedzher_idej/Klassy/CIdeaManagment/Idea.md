[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagment](/api_help/ideamanagment/reference/cideamanagment/index.php)

Idea (доступен с 11.5.0)

Idea
====

```
function
CIdeaManagment::Idea(
	(int)$IdeaId = false
);Копировать
```

Возвращает объект для работы с конкретной идеей указанной во входном параметре. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| IdeaId | ID идеи. По умолчанию - *false*. |

#### Возвращаемое значение

Объект менеджера идей для работы с идеей (*CIdeaManagmentIdea*).

#### Примеры использования

```
$Idea = CIdeaManagment::getInstance()->Idea(1);Копировать
```

Новинки документации в соцсетях:
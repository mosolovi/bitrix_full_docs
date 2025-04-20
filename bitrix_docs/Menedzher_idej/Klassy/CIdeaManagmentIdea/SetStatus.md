[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagmentIdea](/api_help/ideamanagment/reference/cideamanagmentidea/index.php)

SetStatus (доступен с 11.5.0)

SetStatus
=========

```
function
CIdeaManagmentIdea::SetStatus(
	StatusId
);Копировать
```

Устанавливает статус конкретной идеи. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| StatusId | Статус идеи. |

#### Возвращаемое значение

На выходе - *bool*.

#### Примеры использования

```
$b = CIdeaManagment::getInstance()->Idea(1)->SetStatus(2);
if($b)
	echo 'Идеи с ID=1 установлен статус с ID=2.';Копировать
```

Новинки документации в соцсетях:
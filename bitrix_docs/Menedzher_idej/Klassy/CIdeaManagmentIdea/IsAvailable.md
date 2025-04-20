[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagmentIdea](/api_help/ideamanagment/reference/cideamanagmentidea/index.php)

IsAvailable (доступен с 11.5.0)

IsAvailable
===========

```
function
CIdeaManagmentIdea::IsAvailable(
);Копировать
```

Проверяет доступность идеи для последующих операций с ней. На входе - *null*. Нестатический метод.

#### Возвращаемое значение

На выходе - *bool*.

#### Примеры использования

```
if(CIdeaManagment::getInstance()->Idea(1)->IsAvailable())
	echo 'Идея с ID=1 готова к работе.'; Копировать
```

Новинки документации в соцсетях:
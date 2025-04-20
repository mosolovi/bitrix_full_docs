[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagmentIdeaComment](/api_help/ideamanagment/reference/cideamanagmentideacomment/index.php)

Bind (доступен с 11.5.0)

Bind
====

```
function
CIdeaManagmentIdeaComment::Bind();Копировать
```

Помечает комментарий как официальный ответ. на входе - *null*. Нестатический метод.

#### Возвращаемое значение

На выходе - *bool*.

#### Примеры использования

```
if(CIdeaManagment::getInstance()->IdeaComment()->SetID(1)->Bind())
	echo 'Комментарий идеи с ID=1 помечен как официальный ответ';Копировать
```

Новинки документации в соцсетях:
[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagmentIdeaComment](/api_help/ideamanagment/reference/cideamanagmentideacomment/index.php)

UnBind (доступен с 11.5.0)

UnBind
======

```
function
CIdeaManagmentIdeaComment::UnBind();Копировать
```

Снимает метку официального ответа. На входе - *null*. Нестатический метод.

#### Возвращаемое значение

На выходе - *bool*.

#### Примеры использования

```
if(CIdeaManagment::getInstance()->IdeaComment()->SetID(1)->UnBind())
	echo 'Комментарий идеи с ID=1 более не официальный';Копировать
```

Новинки документации в соцсетях:
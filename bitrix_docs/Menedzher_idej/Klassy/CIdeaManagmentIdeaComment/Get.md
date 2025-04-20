[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagmentIdeaComment](/api_help/ideamanagment/reference/cideamanagmentideacomment/index.php)

Get (доступен с 11.5.0)

Get
===

```
function
CIdeaManagmentIdeaComment::Get();Копировать
```

Возвращает информацию по комментарию к идеи. На входе - *null*. Нестатический метод.

#### Возвращаемое значение

Возвращает массив данных по комментарию к идее.

#### Примеры использования

```
$arIdeaComment = CIdeaManagment::getInstance()->IdeaComment()->SetID(1)->Get(); Копировать
```

Новинки документации в соцсетях:
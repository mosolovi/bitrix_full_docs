[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagmentIdeaComment](/api_help/ideamanagment/reference/cideamanagmentideacomment/index.php)

IsAvailable (доступен с 11.5.0)

IsAvailable
===========

```
function
CIdeaManagmentIdeaComment::IsAvailable(
);Копировать
```

Проверяет доступность комментария идеи для последующих операций с ним. На входе - *null*. Нестатический метод.

#### Возвращаемое значение

На выходе - *bool*.

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)

#### Примеры использования

```
if(CIdeaManagment::getInstance()->IdeaComment(1)->IsAvailable())
	echo 'Комментарий идеи с ID=1 готов к работе.'; 
Копировать
```

Новинки документации в соцсетях:
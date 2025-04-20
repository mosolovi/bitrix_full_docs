[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagment](/api_help/ideamanagment/reference/cideamanagment/index.php)

IsAvailable (доступен с 11.5.0)

IsAvailable
===========

```
function
CIdeaManagment::IsAvailable(
);Копировать
```

Проверяет доступность модулей необходимых для корректной работы Менеджера идей. На входе - *null*. Нестатический метод.

#### Возвращаемое значение

На выходе - *bool*.

#### Примеры использования

```
if(CIdeaManagment::getInstance()->IsAvailable())
	echo 'Менеджер идей готов к работе.'; Копировать
```

Новинки документации в соцсетях:
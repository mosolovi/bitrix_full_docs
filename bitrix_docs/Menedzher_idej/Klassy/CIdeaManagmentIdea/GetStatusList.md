[Менеджер идей](/api_help/ideamanagment/index.php)

[Классы](/api_help/ideamanagment/reference/index.php)

[CIdeaManagmentIdea](/api_help/ideamanagment/reference/cideamanagmentidea/index.php)

GetStatusList (доступен с 11.5.0)

GetStatusList
=============

```
function
CIdeaManagmentIdea::GetStatusList(
	XML_ID = false
);Копировать
```

Возвращает массив всех статусов используемых в менеджере идей. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| XML\_ID | По умолчанию - *false*. |

#### Возвращаемое значение

Массив всех статусов.

#### Примеры использования

```
$arStatus = CIdeaManagment::getInstance()->Idea()->GetStatusList(true);
echo '<pre>'; print_r($arStatus); echo '<pre>';Копировать
```

Новинки документации в соцсетях:
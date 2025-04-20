[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

UpdateGroups (доступен с 3.1.1)

UpdateGroups
============

```
void
CPosting::UpdateGroups(
	int ID,
	array aGroup
);Копировать
```

Метод изменяет информацию о привязке выпуска к группам пользователей. Метод нестатический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |
| aRubric | Массив идентификаторов групп пользователей. |  |

#### Пример использования

```
$posting = new CPosting;
$posting->UpdateGroups($ID, array(1));Копировать
```

Новинки документации в соцсетях:
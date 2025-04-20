[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

UpdateRubrics (доступен с 3.1.1)

UpdateRubrics
=============

```
void
CPosting::UpdateRubrics(
	int ID,
	array aRubric
);Копировать
```

Метод изменяет информацию о привязке выпуска к рубрикам подписки. Метод нестатический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |
| aRubric | Массив идентификаторов рассылок. |  |

#### Пример использования

```
$posting = new CPosting;
$posting->UpdateRubrics($ID, array(1, 2, 3));Копировать
```

  

Новинки документации в соцсетях:

© «Битрикс», 2001-2025, «1С-Битрикс», 2025

Наверх
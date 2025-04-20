[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEvent](/api_help/statistic/classes/cstatevent/index.php)

Delete

Delete
======

```
bool
CStatEvent::Delete(
	int event_id
)Копировать
```

Удаляет указанное [событие](/api_help/statistic/terms.php#event).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *event\_id* | ID удаляемого события. |

#### Возвращаемое значение

Метод возвращает "true" в случае успешного удаления и "false" в случае неудачи.

#### Смотрите также

* [Термин "Событие"](/api_help/statistic/terms.php#event)

#### Примеры использования

```
<?
$event_id = 1;
if (CStatEvent::Delete($event_id)) 
	echo "Событие #".$event_id." успешно удалено.";
?>Копировать
```

Новинки документации в соцсетях:
[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEventType](/api_help/statistic/classes/cstateventtype/index.php)

Delete

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CStatEventType::Delete(
	int type_id
)Копировать
```

Удаляет указанный [тип события](/api_help/statistic/terms.php#event_type), вместе со всеми событиями данного типа.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *type\_id* | ID типа события. |

#### Возвращаемое значение

Метод возвращает "true" в случае успешного удаления типа события, либо "false" в противном случае.

#### Смотрите также

* [Термин "Тип события"](/api_help/statistic/terms.php#event_type)

### Примеры использования

```
<?
$type_id = 1;
if (CStatEventType::Delete($type_id)) 
	echo "Тип события #".$type_id." успешно удалено.";
?>Копировать
```

Новинки документации в соцсетях:
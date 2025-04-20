[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

Add (с версии 11.0.0)

Add
===

```
int Add($settings);Копировать
```

Добавляет новый отчёт. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| settings | Массив с конфигурацией нового отчёта. |

#### Возвращаемое значение

Возвращает идентификатор созданного отчёта, или `false` в случае неудачи.

#### Примеры использования

```
<?
$ID = CReport::Add(
	array(
		'title' => 'Список задач',
		'description' => 'Просто список задач',
		'owner' => 'TASKS',
		'entity' => 'Bitrix\\Tasks\\Task',
		'period' => array(
			'type' => 'month',
			'value' => null
		),
		'select' => array(
			0 => array('name' => 'TITLE'),
			1 => array('name' => 'PRIORITY'),
			2 => array('name' => 'RESPONSIBLE.SHORT_NAME'),
			3 => array('name' => 'STATUS_PSEUDO')
		),
		'filter' => array(),
		'sort' => 0,
		'sort_type' => 'ASC',
		'limit' => null,
		'red_neg_vals' => false,
		'grouping_mode' => false,
		'chart' => null
	)
);
?>Копировать
```

Новинки документации в соцсетях:
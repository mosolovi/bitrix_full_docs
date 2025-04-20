[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

Update (с версии 11.0.0)

Update
======

```
int Update($ID, $settings);Копировать
```

Изменяет существующий отчёт.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$ID* | Идентификатор отчёта для изменения. |
| *$settings* | Массив с изменённой конфигурацией отчёта. |

#### Возвращаемое значение

Возвращает экземпляр [CDBResult](/api_help/main/reference/cdbresult/index.php) выполненного запроса на изменение, или `false` в случае неудачи.

#### Примеры использования

```
<?
$ID = CReport::Update(
	159,
	array(
		'title' => 'Список задач',
		'description' => 'Просто список задач с датой создания',
		'owner' => 'TASKS',
		'entity' => 'Bitrix\\Tasks\\Task',
		'period' => array(
			'type' => 'month',
			'value' => null
		),
		'select' => array(
			4 => array('name' => 'CREATED_DATE'),
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
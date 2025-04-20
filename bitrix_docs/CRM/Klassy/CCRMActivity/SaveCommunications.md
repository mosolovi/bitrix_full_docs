[CRM](/api_help/crm/index.php)

[Классы](/api_help/crm/classes/index.php)

[CCRMActivity](/api_help/crm/classes/crm_activity/index.php)

SaveCommunications (доступен с 12.0.2)

SaveCommunications
==================

```
array
CCrmActivity::SaveCommunications(
	integer ID,
	array arComms,
	array arFields,
	bool registerEvents = true, 
	bool checkPerms = true, 
);Копировать
```

Метод служит для сохранения связей Дела. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор Дела. |
| arComms | Массив коммуникаций Дела (email компании, номер телефона).  ``` $arComms = array( 	array( 		'ID' => 0, 		'TYPE' => 'PHONE', 		'VALUE' => $params['PHONE_NUMBER'], 		'ENTITY_ID' => $crmEntity['ENTITY_ID'], 		'ENTITY_TYPE_ID' => $crmEntity['ENTITY_TYPE'] 	) );Копировать ``` |
| arFields | Массив параметров Дела. |
| registerEvents | Параметр указывает, регистрировать ли Дело в Истории CRM. Может принимать значения *true* или *false*. |
| checkPerms | Параметр проверяет права на Дело. Может принимать значения *true* или *false*. |

#### Возвращаемое значение

Метод возвращает массив связей Дела.

Новинки документации в соцсетях:
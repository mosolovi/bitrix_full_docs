[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

GetRubricList (доступен с 3.0.5)

GetRubricList
=============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CSubscription::GetRubricList(
	int ID
);Копировать
```

Метод возвращает выборку рассылок, на которые подписан данный адрес. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор подписки. |  |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult становятся доступны некоторые [поля объекта "Рассылка"](../crubric/crubric.fields.php). А именно:

* ID - Идентификатор рассылки;
* NAME - Название рассылки;
* SORT - Сортировка в списке;
* LID - Идентификатор сайта;
* ACTIVE - Признак активности рассылки (Y/N).
* VISIBLE - Выводить в списке публичных рассылок (Y/N).

### Примеры использования

```
//array of subscribed categories
function GetRubricArray($ID)
{
	$aSubscrRub = array();
	if($ID>0)
	{
		$subscr_rub = CSubscription::GetRubricList($ID);
		while($subscr_rub_arr = $subscr_rub->Fetch())
			$aSubscrRub[] = $subscr_rub_arr["ID"];
	}
	return $aSubscrRub;
}Копировать
```

Новинки документации в соцсетях:
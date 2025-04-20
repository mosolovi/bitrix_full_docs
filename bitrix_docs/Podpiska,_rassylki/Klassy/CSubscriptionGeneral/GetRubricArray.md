[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

GetRubricArray (доступен с 3.0.5)

GetRubricArray
==============

```
array
CSubscription::GetRubricArray(
	int ID
);Копировать
```

Метод возвращает массив идентификаторов рассылок, на которые подписан данный адрес. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор подписки. |  |

#### Возвращаемые значения

Массив целых чисел, идентификаторы рассылок.

#### Пример использования

```
<?
//shows all subscription categories and checks subscribed one
$aSubscrRub = CSubscription::GetRubricArray($ID);
$rub = CRubric::GetList(
	array("LID"=>"ASC", "SORT"=>"ASC", "NAME"=>"ASC"),
	array("ACTIVE"=>"Y", "LID"=>LANG)
);
while($rub->ExtractFields("r_")):
	$bChecked = in_array($r_ID, $aSubscrRub);
?>
<input type="checkbox"
		name="RUB_ID[]"
		value="<?echo $r_ID?>"<?if($bChecked) echo " checked"?>>
<?echo $r_NAME?><br>
<?
endwhile;
?>Копировать
```

Новинки документации в соцсетях:
[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CRubric](/api_help/subscribe/classes/crubric/index.php)

GetSubscriptionCount (доступен с 5.0.2)

GetSubscriptionCount
====================

```
int
CRubric::GetSubscriptionCount(
	int ID
);Копировать
```

Метод возвращает количество подписчиков на указанную рассылку.
Учитываются как подтвержденные, так и неподтвержденные подписчики. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор рассылки. |  |

#### Возвращаемые значения

целое число, равное количеству подписчиков рассылки. Если подписка с заданным идентификатором не существует, то возвращается 0.

#### Пример использования

```
<?
//get site's newsletter categories
$rub = CRubric::GetList(array("SORT"=>"ASC", "NAME"=>"ASC"), array("ACTIVE"=>"Y", "LID"=>LANG));
while($rub->ExtractFields("r_")):
?>
	<input type="checkbox" name="sf_RUB_ID[]" value="<?echo $r_ID?>">
	<?echo $r_NAME?> (<?echo CRubric::GetSubscriptionCount($r_ID);?>)<br>
<?
endwhile;
?>Копировать
```

Новинки документации в соцсетях:
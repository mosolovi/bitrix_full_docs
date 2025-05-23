[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleTax](/api_help/sale/classes/csaletax/index.php)

GetExemptList (доступен с 3.3.1)

GetExemptList
=============

Включить вкладки

Описание и параметры

Возвращаемые значения

Пример использования

### Описание и параметры

```
CDBResult
CSaleTax::GetExemptList(
	array arFilter = array()
);Копировать
```

Метод возвращает набор записей из таблицы освобождений от уплаты налогов, удовлетворяющих фильтру arFilter. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arFilter | Ассоциативный массив для фильтрации записей. Ключами являются названия фильтруемых параметров, а значениями - условия на значения.   Допустимые ключи:  * **GROUP\_ID** - код группы пользователей, которая освобождается от уплаты налога; * **TAX\_ID** - код налога, от уплаты которого освобождается группа пользователей. |

### Возвращаемые значения

Возвращается объект класса CDBResult, содержащий ассоциативные массивы параметров налогов с ключами:

| Ключ | Описание |
| --- | --- |
| GROUP\_ID | Код группы пользователей, которая освобождается от уплаты налога. |
| TAX\_ID | Код налога, от уплаты которого освобождается группа пользователей. |

### Пример использования

```
<?
// Заполним массив налогов, от уплаты которых освобожден текущий пользователь
$arTaxExempt = array();
if ($USER->IsAuthorized())
{
	$arUserGroups = $USER->GetUserGroupArray();
	for ($ig = 0; $ig < count($arUserGroups); $ig++)
	{
		$db_tax_ex_tmp = CSaleTax::GetExemptList(Array("GROUP_ID"=>$arUserGroups[$ig]));
		while ($ar_tax_ex_tmp = $db_tax_ex_tmp->Fetch())
		{
			if (!in_array(IntVal($ar_tax_ex_tmp["TAX_ID"]), $arTaxExempt))
			{
				$arTaxExempt[] = IntVal($ar_tax_ex_tmp["TAX_ID"]);
			}
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях:
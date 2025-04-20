[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleUserAccount](/api_help/sale/classes/csaleuseraccount/index.php)

Withdraw (доступен с 4.0.6)

Withdraw
========

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
double
CSaleUserAccount::Withdraw(
	int userID,
	double paySum,
	string payCurrency[,
	int orderID = 0]
);Копировать
```

Метод снимает указанную сумму с внутреннего счета пользователя. Если на внутреннем счете не достаточно средств, то снимается максимально доступная сумма (т.е. все доступные средства). Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| userID | Код пользователя. |
| paySum | Снимаемая сумма. |
| payCurrency | Валюта снимаемой суммы. |
| orderID | Код заказа, если снятие денег относится к заказу. |

#### Возвращаемые значения

Метод возвращает реально снятую со счета сумму или *false* в случае ошибки.

**Замечание:** деньги снимаются только со счета той же валюты, которая передается параметром в метод. Счета пользователя в другой валюте не затрагиваются.

### Пример использования

```
<?
// Оплатим полностью или хотя бы частично заказ номер 21 со счета пользователя
$arOrder = CSaleOrder::GetByID(21);
$withdrawSum = CSaleUserAccount::Withdraw(
	$arOrder["USER_ID"],
	$arOrder["PRICE"],
	$arOrder["CURRENCY"],
	$arOrder["ID"]
);
if ($withdrawSum > 0)
{
	$arFields = array(
		"SUM_PAID" => $withdrawSum,
		"USER_ID" => $arOrder["USER_ID"]
	);
	CSaleOrder::Update($arOrder["ID"], $arFields);
	if ($withdrawSum == $arOrder["PRICE"])
		CSaleOrder::PayOrder($arOrder["ID"], "Y", False, False);
}
?>Копировать
```

Новинки документации в соцсетях:
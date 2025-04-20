[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleUserCards](/api_help/sale/classes/csaleusercards/index.php)

IdentifyCardType (доступен с 4.0.6)

IdentifyCardType
================

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
string
CSaleUserCards::IdentifyCardType(
	string ccNum
);Копировать
```

Метод определяет тип пластиковой карты по ее номеру. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ccNum | Номер карты. |

#### Возвращаемые значения

Метод возвращает тип карты.

### Пример использования

```
<?
// Сохраним новую карту текущего пользователя
if (CSaleUserCards::CheckPassword())
{
	$arFields = array(
		"USER_ID" => $USER->GetID(),
		"ACTIVE" => "Y",
		"SORT" => "100",
		"PAY_SYSTEM_ACTION_ID" => 11,
		"CURRENCY" => "USD",
		"CARD_TYPE" => CSaleUserCards::IdentifyCardType("4111111111111"),
		"CARD_NUM" => CSaleUserCards::CryptData("4111111111111", "E"),
		"CARD_EXP_MONTH" => 11,
		"CARD_EXP_YEAR" => 2007,
		"DESCRIPTION" => False,
		"CARD_CODE" => "123",
		"SUM_MIN" => False,
		"SUM_MAX" => False,
		"SUM_CURRENCY" => False
	);
	$UserCardID = CSaleUserCards::Add($arFields);
}
?>Копировать
```

Новинки документации в соцсетях:
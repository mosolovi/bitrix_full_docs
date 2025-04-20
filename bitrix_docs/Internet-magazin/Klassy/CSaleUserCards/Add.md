[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleUserCards](/api_help/sale/classes/csaleusercards/index.php)

Add (доступен с 4.0.6)

Add
===

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
int
CSaleUserCards::Add(
	array arFields
);Копировать
```

Метод сохраняет информацию о новой пластиковой карте пользователя. Нестатический метод.

#### Параметры

| Параметр | Описание |
| --- | --- |
| arFields | Ассоциативный массив параметров пластиковой карты с ключами:  * **USER\_ID** - код пользователя; * **SORT** - индекс сортировки; * **PAY\_SYSTEM\_ACTION\_ID** - код обработчика платежной системы; * **CURRENCY** - валюта, которую можно снимать с карты; * **CARD\_CODE** - CVC2; * **CARD\_TYPE** - тип карты; * **CARD\_NUM** - номер карты; * **CARD\_EXP\_MONTH** - месяц окончания действия карты; * **CARD\_EXP\_YEAR** - год окончания действия карты; * **DESCRIPTION** - краткое описание; * **SUM\_MIN** - минимальная сумма, которую можно снять с карты за раз; * **SUM\_MAX** - максимальная сумма, которую можно снять с карты за раз; * **SUM\_CURRENCY** - валюта минимальной и максимальной сумм; * **LAST\_STATUS** - статус последнего использования карты; * **LAST\_STATUS\_CODE** - код статуса последнего использования карты; * **LAST\_STATUS\_DESCRIPTION** - описание статуса последнего использования карты; * **LAST\_STATUS\_MESSAGE** - сообщение платежной системы; * **LAST\_SUM** - последняя снятая с карты сумма; * **LAST\_CURRENCY** - валюта последней снятой с карты суммы; * **ACTIVE** - флаг активности; * **LAST\_DATE** - дата последнего использования карты.     **Замечание:** перед добавлением записи номер карты должен быть зашифрован методом [CSaleUserCards::CryptData](/api_help/sale/classes/csaleusercards/csaleusercards.cryptdata.php). |

#### Возвращаемые значения

Метод возвращает код добавленной записи или *false* в случае ошибки.

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
		"CARD_TYPE" => 
			CSaleUserCards::IdentifyCardType("4111111111111"),
		"CARD_NUM" => 
			CSaleUserCards::CryptData("4111111111111", "E"),
		"CARD_EXP_MONTH" => 11,
		"CARD_EXP_YEAR" => 2007,
		"DESCRIPTION" => false,
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
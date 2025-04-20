[Валюты](/api_help/currency/index.php)

[Классы](/api_help/currency/developer/index.php)

[CCurrencyRates](/api_help/currency/developer/ccurrencyrates/index.php)

ConvertCurrency (3.3.2)

ConvertCurrency
===============

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
float
CCurrencyRates::ConvertCurrency(
	float valSum,
	string curFrom,
	string curTo,
	string valDate = ""
);Копировать
```

Метод переводит сумму valSum из валюты curFrom в валюту curTo по курсу, установленному на дату valDate. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| valSum | Сумма в валюте curFrom, которую нужно перевести в валюту curTo |
| curFrom | Исходная валюта. |
| curTo | Конечная валюта. |
| valDate | Дата, по курсу на которую нужно осуществить перевод. Если дата пуста, то перевод идет по текущему курсу. Необязательный параметр. |

#### Возвращаемые значения

Сумма в новой валюте

### Пример использования

```
<?
// предполагаем, что валюты USD и EUR существуют в базе
$val = 11.95; // сумма в USD
$newval = CCurrencyRates::ConvertCurrency($val, "USD", "EUR");
echo $val." USD = ".$newval." EUR";
?>Копировать
```

```
<?
// способ конвертации валюты для списка
if (CModule::IncludeModule('currency')) {
	$factor = CCurrencyRates::GetConvertFactor('UEE', 'RUB');
} else {
	$factor = 1;
}
foreach ($arResult['ITEMS'] as $i => &$arItem) {
	$arItem['PROPERTY_PRICE_VALUE'] = number_format($arItem['PROPERTY_PRICE_VALUE'] * $factor, 0, '.', ' ');
}
?>Копировать
```

Новинки документации в соцсетях:
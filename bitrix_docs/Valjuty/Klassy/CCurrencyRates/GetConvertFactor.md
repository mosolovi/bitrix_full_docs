[Валюты](/api_help/currency/index.php)

[Классы](/api_help/currency/developer/index.php)

[CCurrencyRates](/api_help/currency/developer/ccurrencyrates/index.php)

GetConvertFactor (с версии 3.3.2 до версии 16.0.0)

GetConvertFactor
================

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
float
CCurrencyRates::GetConvertFactor(
	string curFrom, 
	string curTo, 
	string valDate = ""
);Копировать
```

Метод возвращает коэффициент для перевода сумм из валюты curFrom в валюту curTo по курсу, установленному на дату valDate. Метод статический.

С версии 16.0.0 вместо этого метода используйте [GetConvertFactorEx](/api_help/currency/developer/ccurrencyrates/getconvertfactorex.php).

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| curFrom | Исходная валюта. |
| curTo | Валюта назначения. |
| valDate | Дата, по курсу на которую нужно осуществить перевод. Если дата пуста, то перевод идет по текущему курсу. Необязательный параметр.   Дата должна быть указана в формате **YYYY-MM-DD**. |

#### Возвращаемые значения

Коэффициент для перевода.

### Пример использования

```
<?
$arVals = array(11.95, 18.27, 5.01);
$rate_cost = CCurrencyRates::GetConvertFactor("RUR", "USD");
for ($i = 0; $i < count($arVals); $i++)
{
	echo $arVals[$i]." RUR = ".Round($rate_cost*$arVals[$i], 2)." USD";
}
?>Копировать
```

Новинки документации в соцсетях:
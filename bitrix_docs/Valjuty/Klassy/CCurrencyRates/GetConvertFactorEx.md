[Валюты](/api_help/currency/index.php)

[Классы](/api_help/currency/developer/index.php)

[CCurrencyRates](/api_help/currency/developer/ccurrencyrates/index.php)

GetConvertFactorEx (доступен с 11.5.0)

GetConvertFactorEx
==================

```
float
CCurrencyRates::GetConvertFactorEx(
	string curFrom, 
	string curTo, 
	string valDate = ""
);Копировать
```

Метод возвращает коэффициент для перевода сумм из валюты curFrom в валюту curTo по курсу, установленному на дату valDate. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| curFrom | Исходная валюта. |
| curTo | Валюта назначения. |
| valDate | Дата, по курсу на которую нужно осуществить перевод. Если дата пуста, то перевод идет по текущему курсу. Необязательный параметр.   Дата должна быть указана в формате **YYYY-MM-DD**. |

#### Возвращаемые значения

Коэффициент для перевода.

Новинки документации в соцсетях:
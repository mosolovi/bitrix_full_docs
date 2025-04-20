[Валюты](/api_help/currency/index.php)

[Классы](/api_help/currency/developer/index.php)

[CCurrencyLang](/api_help/currency/developer/ccurrencylang/index.php)

CurrencyFormat (доступен с 14.0.0)

CurrencyFormat
==============

```
string
CCurrencyLang::CurrencyFormat(
	float price, 
	string currency,
	bool useTemplate
);Копировать
```

Форматирует цену в соответствии с настройками валюты. В случае вызова в административной части дополнительно выполняет очистку формата от тегов и скриптов. Если метод вызывается в публичной части, то будет задействован параметр HIDE\_ZERO, который отвечает за скрытие незначащих нулей в дробной части. Метод статический.

**Примечание:** используется взамен функций [CurrencyFormat](/api_help/currency/functions/currencyformat.php) и [CurrencyFormatNumber](/api_help/currency/functions/currencyformatnumber.php), которые считаются устаревшими с версии модуля **14.0.0**.

#### Параметры метода

| Параметр | Тип | Описание |
| --- | --- | --- |
| price | string    float   int | Цена (денежная сумма), которую нужно сконвертировать. Корректно обрабатываются числа в формате *string*, *float* или *int* (целое число).  В случае, когда значение не может быть описано в рамках типа *float* или *int*, можно передать его в виде *string* (с версии модуля **24.0.0**).    **Примечание.** Обрабатываются только строки вида:    ``` LNUM		[0-9]+ DNUM		([0-9]*[\.]{LNUM}) | ({LNUM}[\.][0-9]*) Копировать ```    Смотрите [документацию](https://www.php.net/manual/ru/language.types.numeric-strings.php) по числовым строкам. Все остальные значения числовых строк будут приведены к *float*.    Например:     ``` $price = '123456789012345678901234567.45'; $currency = 'RUB'; $result = \CCurrencyLang::CurrencyFormat(     $price,     $currency ); echo $result; Копировать ```     выведет (рассматриваем формат по умолчанию для русского языка)     ``` 123 456 789 012 345 678 901 234 567.45 ₽ Копировать ``` |
| currency | string | Код валюты. |
| useTemplate | boolean | Если указано *true*, то работает как [CurrencyFormat](/api_help/currency/functions/currencyformat.php) и вызывается событие [CurrencyFormat](/api_help/currency/events/currencyformat.php). Если задано *false*, то работает как [CurrencyFormatNumber](/api_help/currency/functions/currencyformatnumber.php). |

#### Возвращаемые значения

Возвращает отформатированную строку.

Новинки документации в соцсетях:
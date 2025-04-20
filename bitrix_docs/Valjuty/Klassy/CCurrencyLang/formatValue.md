[Валюты](/api_help/currency/index.php)

[Классы](/api_help/currency/developer/index.php)

[CCurrencyLang](/api_help/currency/developer/ccurrencylang/index.php)

formatValue (доступен с 19.0.0)

formatValue
===========

```

CCurrencyLang::formatValue(
$value, array $format, $useTemplate = true
);Копировать
```

Метод используется для форматирования значения по переданному формату. Статический метод.

Возвращаемое значение – строка.

#### Параметры метода

| Параметр | Тип | Описание |
| --- | --- | --- |
| value | string    float   int | Значение. Корректно обрабатываются числа в формате *string*, *float* или *int* (целое число).  В случае, когда значение не может быть описано в рамках типа *float* или *int*, можно передать его в виде *string* (с версии модуля **24.0.0**).    **Примечание.** Обрабатываются только строки вида:    ``` LNUM		[0-9]+ DNUM		([0-9]*[\.]{LNUM}) | ({LNUM}[\.][0-9]*) Копировать ```    Смотрите [документацию](https://www.php.net/manual/ru/language.types.numeric-strings.php) по числовым строкам. Все остальные значения числовых строк будут приведены к *float*.    Например:     ``` $value = '123456789012345678901234567.45'; $currency = 'RUB'; $result = \CCurrencyLang::formatValue( 	$value, 	\CCurrencyLang::GetFormatDescription($currency) ); echo $result; Копировать ```     выведет (рассматриваем формат по умолчанию для русского языка)     ``` 123 456 789 012 345 678 901 234 567.45 ₽ Копировать ``` |
| format | array | Формат. |
| useTemplate | boolean | Использовать шаблон или нет.  Если указано *true*, то работает как [CurrencyFormat](/api_help/currency/functions/currencyformat.php) и вызывается событие [CurrencyFormat](/api_help/currency/events/currencyformat.php). Если задано *false*, то работает как [CurrencyFormatNumber](/api_help/currency/functions/currencyformatnumber.php). |

Новинки документации в соцсетях:
[Валюты](/api_help/currency/index.php)

[Классы](/api_help/currency/developer/index.php)

[CCurrencyLang](/api_help/currency/developer/ccurrencylang/index.php)

GetCurrencyFormat (3.3.2)

GetCurrencyFormat
=================

Включить вкладки

Описание и параметры

Возвращаемые значения

Пример использования

### Описание и параметры

```
array
CCurrencyLang::GetCurrencyFormat(
	string currency, 
	string lang = LANGUAGE_ID
);Копировать
```

Метод возвращает массив языкозависимых параметров валюты currency для языка lang.

Метод аналогичен методу [CCurrencyLang::GetByID](/api_help/currency/developer/ccurrencylang/ccurrencylang__getbyid.9828270a.php), за исключение того, что возвращаемый результат в методе CCurrencyLang::GetCurrencyFormat кешируется. Поэтому повторный вызов метода с теми же кодами валюты и языка в рамках одной страницы не приводит к дополнительному запросу к базе данных. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| currency | Код валюты, языкозависимые параметры которой нужны. |
| lang | Код языка. Необязательный параметр. |

### Возвращаемые значения

Ассоциативный массив с ключами:

| Ключ | Описание |
| --- | --- |
| CURRENCY | Код валюты (трехсимвольный) |
| LID | Код языка. |
| FORMAT\_STRING | Строка формата, в соответствии с которой выводится суммы в этой валюте на этом языке. |
| FULL\_NAME | Полное название валюты. |
| DEC\_POINT | Символ, являющийся десятичной точкой при выводе сумм. |
| THOUSANDS\_SEP | Разделитель тысяч при выводе. |
| DECIMALS | Количество знаков после запятой при выводе. |
| HIDE\_ZERO | (Y|N) Определяет скрывать или показывать незначащие нули в дробной части (результат будет виден только в публичной части). |

### Пример использования

```
<?
function MyFormatCurrency($fSum, $strCurrency)
{
	if (!isset($fSum) || strlen($fSum)<=0)
		return "";
	$arCurFormat = CCurrencyLang::GetCurrencyFormat($strCurrency);
	if (!isset($arCurFormat["DECIMALS"]))
		$arCurFormat["DECIMALS"] = 2;
	$arCurFormat["DECIMALS"] = IntVal($arCurFormat["DECIMALS"]);
	if (!isset($arCurFormat["DEC_POINT"]))
		$arCurFormat["DEC_POINT"] = ".";
	if (!isset($arCurFormat["THOUSANDS_SEP"]))
		$arCurFormat["THOUSANDS_SEP"] = "\\"."xA0";
	if (!isset($arCurFormat["FORMAT_STRING"]))
		$arCurFormat["FORMAT_STRING"] = "#";
	$num = number_format(
		$fSum,
		$arCurFormat["DECIMALS"],
		$arCurFormat["DEC_POINT"],
		$arCurFormat["THOUSANDS_SEP"]
	);
	return str_replace(
		"#",
		$num,
		$arCurFormat["FORMAT_STRING"]
	);
}
echo "Сумма 11800.95 руб на текущем языке будет выглядеть так: ";
echo MyFormatCurrency(11800.95, "RUR");
?>Копировать
```

Новинки документации в соцсетях:
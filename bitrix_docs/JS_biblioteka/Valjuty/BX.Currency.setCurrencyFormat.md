[JS библиотека](/api_help/js_lib/index.php)

[Валюты](/api_help/js_lib/currency/index.php)

BX.Currency.setCurrencyFormat

BX.Currency.setCurrencyFormat
=============================

```
BX.Currency.setCurrencyFormat(
	currency, format, replace
);Копировать
```

Функция задаёт формат конкретной валюты.

#### Параметры функции

| Параметр | Описание | Тип |
| --- | --- | --- |
| currency | Код валюты. | string |
| format | Описание [формата.](/api_help/js_lib/currency/index.php) | object |
| replace | Переписывать ли формат, если уже задан. | bool |

#### Возвращаемое значение

Нет.

#### Примеры:

```
<? 
CJSCore::Init(array('currency')); 
 
$currencyFormat = CCurrencyLang::GetFormatDescription('RUB'); 
?> 
<script type="text/javascript"> 
BX.Currency.setCurrencyFormat('RUB', <? echo CUtil::PhpToJSObject($currencyFormat, false, true); ?>);  
var formatRub = BX.Currency.currencyFormat(121.50, 'RUB', true);  
alert(formatRub); 
</script>Копировать
```

Новинки документации в соцсетях:
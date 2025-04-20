[JS библиотека](/api_help/js_lib/index.php)

[Валюты](/api_help/js_lib/currency/index.php)

BX.Currency.currencyFormat

BX.Currency.currencyFormat
==========================

```
BX.Currency.currencyFormat(
	price, currency, useTemplate
);Копировать
```

Функция форматирует цену.

#### Параметры функции

| Параметр | Описание | Тип |
| --- | --- | --- |
| price | Значение цены. | string, int, float |
| currency | Код валюты. | string |
| useTemplate | Использовать ли шаблон. Доступные значения:  * `false` – выводить только значение цены; * `true` – выводить полностью отформатированную цену. | bool |

#### Возвращаемое значение

Строка.

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
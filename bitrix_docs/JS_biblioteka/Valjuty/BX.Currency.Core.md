[JS библиотека](/api_help/js_lib/index.php)

[Валюты](/api_help/js_lib/currency/index.php)

BX.Currency.Core (доступно с 20.100.0)

BX.Currency.Core
================

Расширение ES6 для работы с валютами и их форматами.

#### BX.Currency.Core

#### Методы

| Метод | Описание | С версии |
| --- | --- | --- |
| `BX.Currency.Core.getCurrencyList(): CurrencyItem[]` | Статический метод. Возвращает внутренний список валют. |  |
| `BX.Currency.Core.setCurrencyFormat(currency: string, format, replace: boolean): void` | Статический метод. Задаёт формат конкретной валюты. Параметры:  * `currency` - код валюты; * `format` - формат валюты в виде [CCurrencyLang::GetFormatDescription()](/api_help/currency/developer/ccurrencylang/getformatdescription.php); * `replace` - перезаписать формат, если уже задан. |  |
| `BX.Currency.Core.setCurrencies(currencies: [], replace: boolean)` | Статический метод. Задаёт форматы нескольких валют сразу. Параметры:  * `currencies` - список валют с форматами. Каждый элемент массива – объект с двумя полями:   + `CURRENCY` - код валюты;   + `FORMAT` - описание формата в виде [CCurrencyLang::GetFormatDescription()](/api_help/currency/developer/ccurrencylang/getformatdescription.php). * `replace` - перезаписать формат, если уже задан. |  |
| `BX.Currency.Core.getCurrencyFormat(currency: string)` | Статический метод. Возвращает формат валюты. Параметры:  * `currency` - код валюты. |  |
| `BX.Currency.Core.getCurrencyIndex(currency: string): number` | Статический метод. Возвращает расположение валюты во внутреннем списке валют. Параметры:  * `currency` - код валюты. |  |
| `BX.Currency.Core.getPriceControl(control: Element, currency: string)` | Статический метод. Позволяет форматировать валюту, взяв в качестве числового значения HTML-элемент. Параметры:  * `control` - то, что будет подставлено в строку шаблона формата валюты на место числа; * `currency` - код валюты.   Пример:  на странице есть элемент `<h1 id="currency">3000</h1>`:  ``` const el = document.getElementById('currency'); CurrencyCore.getPriceControl(el, 'RUB'); // вернёт строку "<h1 id="currency">3000</h1> ₽" Копировать ``` | 22.500.0 |
| `BX.Currency.Core.clearCurrency(currency: string): number` | Статический метод. Удаляет формат валюты по коду из внутреннего списка (если он есть). Параметры:  * `currency` - код валюты. |  |
| `BX.Currency.Core.clean()` | Статический метод. Очищает внутренний список. |  |
| `BX.Currency.Core.currencyFormat(price: number, currency: string, useTemplate: boolean)` | Статический метод. Форматирует цену. Параметры:  * `price` - значение цены; * `currency` - код валюты; * `useTemplate` - использовать ли шаблон. Доступные значения:   + `false` - выводить только значение цены;   + `true` - выводить полностью отформатированную цену. |  |
| `BX.Currency.Core.loadCurrencyFormat(currency)` | Статический метод. Асинхронная загрузка формата. Параметры:  * `currency` - код валюты. |  |

#### Пример

```
example.js
import {CurrencyCore} from 'currency.currency-core';
export class Example
{
	constructor(currencyId: string)
	{
		this.currencyFormat = CurrencyCore.loadCurrencyFormat(currencyId);
	}
}Копировать
```

Новинки документации в соцсетях:
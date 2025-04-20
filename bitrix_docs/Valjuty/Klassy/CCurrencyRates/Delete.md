[Валюты](/api_help/currency/index.php)

[Классы](/api_help/currency/developer/index.php)

[CCurrencyRates](/api_help/currency/developer/ccurrencyrates/index.php)

Delete (3.3.2)

Delete
======

```
bool
CCurrencyRates::Delete(
	int ID
);Копировать
```

Удаляет запись с кодом ID из таблицы курсов валют. Если удаляется несуществующий курс (нет курса с таким ID) - будет ошибка. Метод статический.

В случае успеха сбросится кеш **currency\_rate** и тэгированный **currency\_id\_КОД\_ВАЛЮТЫ**.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код записи для удаления. |

#### Возвращаемые значения

Возвращает значение *True* в случае успешного добавления и *False* - в противном случае. Текст ошибки выводится с помощью `$APPLICATION->GetException`.

Новинки документации в соцсетях:
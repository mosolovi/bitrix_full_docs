[Валюты](/api_help/currency/index.php)

[Классы](/api_help/currency/developer/index.php)

[CCurrency](/api_help/currency/developer/ccurrency/index.php)

Delete (3.3.2)

Delete
======

```
bool
CCurrency::Delete(
	string currency
);Копировать
```

Статический метод удаляет валюту с кодом **currency**. Удаляются в том числе все введенные курсы для этой валюты, а так же языкозависимые свойства валюты.

Перед удалением вызывает событие **OnBeforeCurrencyDelete**, где можно отменить удаление. Формат обработчика: `boolean Handler($currency)`.

Сбрасывает кеш **currency\_currency\_list** и **currency\_base\_currency**. Так же сбросит тегированный кеш **currency\_id\_КОД\_ВАЛЮТЫ**.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| currency | Код валюты. |

#### Возвращаемые значения

Метод возвращает *True* в случае успешного удаления и *False* - в противном случае

#### Пример использования

```
<?
CCurrency::Delete("USD");
?>Копировать
```

Новинки документации в соцсетях:
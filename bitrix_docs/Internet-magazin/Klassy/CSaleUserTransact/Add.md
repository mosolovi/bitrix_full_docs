[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleUserTransact](/api_help/sale/classes/csaleusertransact/index.php)

Add (доступен с 4.0.6)

Add
===

```
int
CSaleUserTransact::Add(
	array arFields
);Копировать
```

Метод добавляет новую транзакцию с параметрами из массива arFields. Нестатический метод.

Добавление транзакции не влияет на состояние счёта пользователя. Для изменения счёта используйте [CSaleUserAccount::UpdateAccount](/api_help/sale/classes/csaleuseraccount/csaleuseraccount.updateaccount.php)

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arFields | Ассоциативный массив параметров новой транзакции с ключами:  * **USER\_ID** - код пользователя; * **AMOUNT** - сумма; * **CURRENCY** - валюта суммы; * **DEBIT** - "Y", если занесение денег на счет, и   "N", если списание денег со счета; * **DESCRIPTION** - описание; * **ORDER\_ID** - код заказа, если транзакция относится к заказу; * **EMPLOYEE\_ID** - код пользователя, осуществившего транзакцию; * **TRANSACT\_DATE** - дата транзакции. |

#### Возвращаемые значения

Метод возвращает код вставленной транзакции или *false* в случае ошибки.

Новинки документации в соцсетях:
[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleTax](/api_help/sale/classes/csaletax/index.php)

Update (доступен с 3.3.1)

Update
======

```
int
CSaleTax::Update(
	int ID,
	array arFields
);Копировать
```

Метод обновляет параметры налога с кодом ID. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код налога. |
| arFields | Ассоциативный массив новых параметров налога, ключами в котором являются названия параметров, а значениями - соответствующие значения.   Допустимые параметры:  * **LID** - сайт; * **NAME** - название налога; * **DESCRIPTION** - описание; * **CODE** - символьный код. |

#### Возвращаемые значения

Метод возвращает код измененного налога или *false* в случае ошибки.

Новинки документации в соцсетях:
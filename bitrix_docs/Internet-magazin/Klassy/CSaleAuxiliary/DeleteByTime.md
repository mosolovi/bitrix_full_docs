[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleAuxiliary](/api_help/sale/classes/csaleauxiliary/index.php)

DeleteByTime (доступен с 4.0.10)

DeleteByTime
============

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
bool
CSaleAuxiliary::DeleteByTime(
	int periodLength,
	sring periodType
);Копировать
```

Метод удаляет всю информацию о временном доступе, которая старше указанного времени. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| periodLength | Длина периода времени, в течение которого пользователь имеет доступ к ресурсу. |
| periodType | Тип длины периода времени, в течение которого пользователь имеет доступ к ресурсу. Допустимые значения:  * I - минута; * H - час; * D - сутки; * W - неделя; * M - месяц; * Q - квартал; * S - полугодие; * Y - год. |

#### Возвращаемые значения

*true* в случае успешного удаления и *false* в противном случае.

### Пример использования

```
<?
// Удалим все записи старше 2 дней
CSaleAuxiliary::DeleteByTime(2, "D");
?>Копировать
```

Новинки документации в соцсетях:
[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleAuxiliary](/api_help/sale/classes/csaleauxiliary/index.php)

CheckAccess (доступен с 4.0.10)

CheckAccess
===========

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
bool
CSaleAuxiliary::CheckAccess(
	int userID,
	string itemMD5,
	int periodLength,
	string periodType
);Копировать
```

Метод проверяет, может ли посетитель с кодом userID получить доступ к ресурсу с идентифицирующей строкой itemMD5. Период, в течение которого пользователь имеет доступ к ресурсу, задается длиной periodLength и типом periodType. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| userID | Код пользователя. |
| itemMD5 | Строка, однозначно идентифицирующая ресурс (идентификатор ресурса). |
| periodLength | Длина периода, в течение которого пользователь имеет доступ к ресурсу. |
| periodType | Тип длины периода, в течение которого пользователь имеет доступ к ресурсу. Допустимые значения: I - минута, H - час, D - сутки, W - неделя, M - месяц, Q - квартал, S - полугодие, Y - год. |

#### Возвращаемые значения

*true*, если пользователь может получить доступ к данному ресурсу, и *false* - в противном случае.

### Пример использования

```
<?
if (CSaleAuxiliary::CheckAccess($USER->GetID(), "pict.jpg", 2, "D"))
{
	echo '<a href="'.pict.jpg.'">Файл доступен для скачивания</a>';
}
else
{
	echo "Файл не доступен для скачивания";
}
?>Копировать
```

Новинки документации в соцсетях:
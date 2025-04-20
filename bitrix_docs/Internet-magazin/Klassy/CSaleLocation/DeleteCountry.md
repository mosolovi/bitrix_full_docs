[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocation](/api_help/sale/classes/csalelocation/index.php)

DeleteCountry (доступен с 3.2.2, устарел с 14.10)

DeleteCountry
=============

Класс устарел. Рекомендуется использовать методы класса [Bitrix\Sale\Location](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/location/index.php).

```
bool
CSaleLocation::DeleteCountry(
	int ID
);Копировать
```

Метод удаляет страну с кодом ID. Связанные с этой страной местоположения не изменяются. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код страны. |

#### Возвращаемые значения

Метод возвращает *true* в случае успешного удаления местоположения и *false* - в противном случае.

#### Пример использования

```
<?
if (!CSaleLocation::DeleteCountry(12))
	echo "Ошибка удаления страны";
?>Копировать
```

Новинки документации в соцсетях:
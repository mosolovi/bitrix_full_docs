[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocation](/api_help/sale/classes/csalelocation/index.php)

DeleteCity (доступен с 3.2.2, устарел с 14.10)

DeleteCity
==========

Класс устарел. Рекомендуется использовать методы класса [Bitrix\Sale\Location](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/location/index.php).

```
bool
CSaleLocation::DeleteCity(
	int ID
);Копировать
```

Метод удаляет город с кодом ID. Местоположение, с которым связан этот город, не изменяется. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код города. |

#### Возвращаемые значения

Метод возвращает *true* в случае успешного удаления местоположения и *false* - в противном случае.

#### Пример использования

```
<?
if (!CSaleLocation::DeleteCity(12))
	echo "Ошибка удаления города";
?>Копировать
```

Новинки документации в соцсетях:
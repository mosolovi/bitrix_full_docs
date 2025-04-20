[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvType](/api_help/advertising/classes/cadvtype/index.php)

GetByID (3.3.4)

GetByID
=======

```
record set
CAdvType::GetByID(
	varchar(255) TYPE_SID
);Копировать
```

Метод возвращает тип баннера по его символьному ID. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| TYPE\_SID | Символьный ID типа. |

#### Пример массива, получаемого после Fetch результата, возвращенного данным методом

```
<?
Array
(
	[SID] => TOP
	[ACTIVE] => Y
	[SORT] => 10
	[NAME] => Top banner
	[DESCRIPTION] => описание типа
	[DATE_CREATE] => 03.06.2004 17:27:00
	[DATE_MODIFY] => 03.06.2004 17:27:00
	[CREATED_BY] => 2
	[MODIFIED_BY] => 2
	[BANNER_COUNT] => 63
)
?>Копировать
```

Новинки документации в соцсетях:
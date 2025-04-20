[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CAdv](/api_help/statistic/classes/cadv/index.php)

GetDropdownList

GetDropdownList
===============

Включить вкладки

Описание и параметры

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CAdv::GetDropdownList(
	string order = "ORDER BY REFERER1, REFERER2"
)Копировать
```

Возвращает список [рекламных кампаний](/api_help/statistic/terms.php#adv) (РК) для вывода его в выпадающем списке с помощью функции [SelectBox](/api_help/main/functions/html/selectbox.php), либо в списке множественного выбора с помощью функции [SelectBoxM](/api_help/main/functions/html/selectboxm.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *order* | SQL код, позволяющий задать произвольную сортировку списка рекламных кампаний. |

#### Смотрите также

* [Термин "Рекламная кампания"](/api_help/statistic/terms.php#adv)
* [CAdv::GetList](/api_help/statistic/classes/cadv/getlist.php)
* [CAdv::GetSimpleList](/api_help/statistic/classes/cadv/getsimplelist.php)
* [SelectBox](/api_help/main/functions/html/selectbox.php)
* [SelectBoxM](/api_help/main/functions/html/selectboxm.php)

### Структура возвращаемой записи

```
Array
(
	[REFERENCE_ID] => ID РК
	[REFERENCE] => [ID РК] referer1 / referer2
)Копировать
```

### Примеры использования

```
<?
// выпадающий список с одиночным выбором
echo SelectBox("ADV_ID", CAdv::GetDropdownList(), "", intval($ADV_ID));
// список из 20 видимых элементов с возможностью множественного выбора
echo SelectBoxM("arADV_ID[]", CAdv::GetDropdownList(), $arADV_ID, "", false, 20);
?>Копировать
```

Новинки документации в соцсетях:
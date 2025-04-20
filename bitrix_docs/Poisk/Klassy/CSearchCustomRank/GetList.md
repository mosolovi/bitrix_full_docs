[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearchCustomRank](/api_help/search/classes/csearchcustomrank/index.php)

GetList (доступен с 5.1.1)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
CDBResult
CSearchCustomRank::GetList(
	array aSort = array(),
	array aFilter = array()
);Копировать
```

Получение списка правил сортировки по фильтру. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| aSort | Массив, содержащий признак сортировки в виде наборов "название поля"=>"направление".    Название поля может принимать значение названия любого из полей [объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php). Не обязательный параметр. По умолчанию равен:  ``` array( 	"SITE_ID"=>"ASC", 	"MODULE_ID"=>"ASC", 	"PARAM1"=>"DESC", 	"PARAM2"=>"DESC", 	"ITEM_ID"=>"DESC", )Копировать ``` |
| aFilter | Массив, содержащий фильтр в виде наборов "название поля"=>"значение фильтра".    Название поля может принимать значение названия любого из полей [объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php). Фильтрация осуществляется по точному совпадению значения фильтра и правила. Не обязательный параметр. |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php).
При выборке из результата методами класса CDBResult становятся доступны поля [объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php).

### Смотрите также

* [Поля объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php)

Новинки документации в соцсетях:
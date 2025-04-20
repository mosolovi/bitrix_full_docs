[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CRubric](/api_help/subscribe/classes/crubric/index.php)

GetList (доступен с 5.0.2)

GetList
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CRubric::GetList(
	array aSort = Array(),
	array aFilter = Array()
);Копировать
```

Метод возвращает список рассылок по фильтру. Метод статический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| aSort | Массив, содержащий признак сортировки в виде наборов "название поля"=>"направление".    Название поля может принимать значение:   * **NAME** - название рассылки; * **LID** - идентификатор сайта; * **ACT** - активность рассылки; * **SORT** - сортировка в списке; * **ID** - идентификатор рассылки; * **AUTO** - флаг генерации; * **VISIBLE** - публичность рассылки; * **LAST\_EXECUTED** - время последней генерации.  Направление сортировки может принимать значение:  * **ASC** - по возрастанию; * **DESC** - по убыванию.  Пример:  ``` array("LID"=>"ASC", "NAME"=>"DESC")Копировать ``` |  |
| aFilter | Массив, содержащий фильтр в виде наборов "название поля"=>"значение фильтра".    Название поля может принимать значение:   * **LID** - идентификатор сайта; * **ACTIVE** - активность рассылки; * **AUTO** - флаг генерации; * **VISIBLE** - публичность рассылки; * **ID** - идентификатор рассылки. * **NAME** - название рассылки.  Пример:  ``` array("LID"=>SITE_ID, "ACTIVE"=>"Y")Копировать ``` |  |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult
становятся доступны [поля объекта "Рассылка"](/api_help/subscribe/classes/crubric/crubric.fields.php).

### Примеры использования

```
<?
//get site's newsletter categories
$rub = CRubric::GetList(array("SORT"=>"ASC", "NAME"=>"ASC"), array("ACTIVE"=>"Y", "LID"=>LANG));
while($rub->ExtractFields("r_")):
?>
	<input type="checkbox" name="sf_RUB_ID[]" value="<?echo $r_ID?>"><?echo $r_NAME?><br>
<?
endwhile;
?>Копировать
```

```
<?
// Вывод рубрик можно производить таким способом
$arOrder = Array("SORT"=>"ASC", "NAME"=>"ASC"); 
$arFilter = Array("ACTIVE"=>"Y", "LID"=>LANG); 
$rsRubric = CRubric::GetList($arOrder, $arFilter); 
$arRubrics = array(); 
while($arRubric = $rsRubric->GetNext()) 
{ 
	$arResult["RUBRIC_LIST"][] = $arRubric; 
} 
?>Копировать
```

Новинки документации в соцсетях:
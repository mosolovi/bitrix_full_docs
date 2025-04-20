[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CAdv](/api_help/statistic/classes/cadv/index.php)

GetSimpleList

GetSimpleList
=============

Включить вкладки

Описание и параметры

Смотрите также

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CAdv::GetSimpleList(
	string &by = "s_referer1",
	string &order = "desc",
	array filter = array(),
	bool &is_filtered
)Копировать
```

Возвращает упрощённый список [рекламных кампаний](/api_help/statistic/terms.php#adv) (РК).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *by* | Поле для сортировки. Возможные значения:  * **s\_id** - ID РК; * **s\_referer1** - [идентификатор](/api_help/statistic/terms.php#adv_id) referer1 РК; * **s\_referer2** - идентификатор referer2 РК; * **s\_description** - описание РК. |
| *оrder* | Порядок сортировки. Возможные значения:  * **asc** - по возрастанию; * **desc** - по убыванию. |
| *filter* | Массив для фильтрации результирующего списка. В массиве допустимы следующие ключи:  * **ID**\* - ID РК; * **ID\_EXACT\_MATCH** - если значение равно "N", то при фильтрации по **ID** будет искаться вхождение; * **REFERER1**\* - идентификатор referer1 РК; * **REFERER1\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **REFERER1** будет искаться точное совпадение; * **REFERER2**\* - идентификатор referer2 РК; * **REFERER2\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **REFERER2** будет искаться точное совпадение; * **DESCRIPTION**\* - описание РК; * **DESCRIPTION\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **DESCRIPTION** будет искаться точное совпадение.  \* - допускается [сложная логика](/api_help/main/general/filter.php) |
| *is\_filtered* | Флаг отфильтрованности списка рекламных кампаний. Если значение равно "true", то список был отфильтрован. |

### Смотрите также

* [Термин "Рекламная кампания"](/api_help/statistic/terms.php#adv)
* [CAdv::GetList](/api_help/statistic/classes/cadv/getlist.php)
* [CAdv::GetDropdownList](/api_help/statistic/classes/cadv/getdropdownlist.php)

### Структура возвращаемой записи

```
Array
(
	[ID] => ID
	[REFERER1] => идентификатор referer1
	[REFERER2] => идентификатор referer2
	[DESCRIPTION] => описание
)Копировать
```

### Примеры использования

```
<?
// выберем только те рекламные кампании у которых в referer1 входит "google"
$arFilter = array(
	"REFERER1" => "google"
);
// получим список записей
$rs = CAdv::GetSimpleList(
	($by="s_referer1"), 
	($order="desc"), 
	$arFilter, 
	$is_filtered
);
// выведем все записи
while ($ar = $rs->Fetch())
{
	echo "<pre>"; print_r($ar); echo "</pre>";    
}
?>Копировать
```

Новинки документации в соцсетях:
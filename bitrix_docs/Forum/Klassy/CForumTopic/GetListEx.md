[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumTopic](/api_help/forum/developer/cforumtopic/index.php)

GetListEx (доступно с 3.3.3)

GetListEx
=========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CForumTopic::GetListEx(
	array arOrder = Array("ID"=>"ASC"),
	array arFilter = Array(),
	bool bCount = false,
	int iNum = 0,
	array arAddParams = Array()
);Копировать
```

Возвращает список тем (включая связаные данные) по фильтру *arFilter*, отсортированый в соответствии с *arOrder*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| arOrder | Массив вида Array(*by1*=>*order1*[, *by2*=>*order2* [, ..]]). Подробное описание параметра смотрите в описании функции [CForumTopic::GetList](/api_help/forum/developer/cforumtopic/getlist.php). |  |
| arFilter | массив вида array("фильтруемое поле"=>"значения фильтра" [, ...]).   Подробное описание параметра смотрите в описании функции [CForumTopic::GetList](/api_help/forum/developer/cforumtopic/getlist.php). |  |
| bCount | Если параметр равен True, то возвращается только количество сообщений, которое соответствует установленному фильтру. Необязательный. По умолчанию равен False. |  |
| iNum | Ограничение числа возвращаемых записей. Если параметр iNum отличен от нуля, то возвращается не более iNum записей. Поддерживается не для всех баз данных. Если параметр не поддерживается, то его установки игнорируются. Необязательный. По умолчанию равен 0. |  |
| arAddParams | Массив параметров. | 4.0.3 |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля темы](/api_help/forum/fields.php#cforumtopic)

### Примеры использования

```
<?
// выберем все опубликованные темы форума с кодом $FID, 
// отсортированные сначала по индексу сортировки, а потом 
// по дате последнего сообщения в теме
$db_res = CForumTopic::GetList(array("SORT"=>"ASC", "LAST_POST_DATE"=>"DESC"), array("FORUM_ID"=>$FID));
while ($ar_res = $db_res->Fetch())
{
	echo "<pre>";
	print_r($ar_res);
	echo "</pre><br>";
}
?>Копировать
```

Новинки документации в соцсетях:
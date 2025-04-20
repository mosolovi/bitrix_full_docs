[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumTopic](/api_help/forum/developer/cforumtopic/index.php)

GetList (доступно с 3.3.3)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CForumTopic::GetList(
	array arOrder = Array("ID"=>"ASC"),
	array arFilter = Array(),
	bool bCount = false,
	int iNum = 0,
	array arAddParams = Array()
);Копировать
```

Возвращает список тем по фильтру *arFilter*, отсортированый в соответствии с *arOrder*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| arOrder | Массив вида Array(*by1*=>*order1*[, *by2*=>*order2* [, ..]]), где    *by* - поле для сортировки, может принимать значения      **ID** - ID темы;      **TITLE** - заголовок темы;      **STATE** - состояние темы;      **USER\_START\_ID** - ID пользователя, который создал тему;      **USER\_START\_NAME** - имя пользователя, который создал тему;      **START\_DATE** - дата создания темы;      **POSTS** - количество ответов в теме;      **VIEWS** - количество просмотров темы;      **APPROVED** - опубликованность темы;      **LAST\_POST\_DATE** - дата последнего сообщения в теме;      **SORT** - индекс сортировки;    *order* - порядок сортировки, может принимать значения      **ASC** - по возрастанию;      **DESC** - по убыванию;   Необязательный. По умолчанию равен Array("SORT"=>"ASC") |  |
| arFilter | массив вида array("фильтруемое поле"=>"значения фильтра" [, ...])  "фильтруемое поле" может принимать значения:  **STATE** - состояние темы;  **FORUM\_ID** - ID форума;  **ID** - ID темы;  **APPROVED** - опубликованность;  **LAST\_POST\_DATE** - дата последнего сообщения в теме;   **USER\_START\_ID** - ID автора темы. фильтруемое поле может иметь содержать перед названием тип проверки фильтра  "!" - не равно  "<" - меньше  "<=" - меньше либо равно  ">" - больше  ">=" - больше либо равно    При необходимости фильтрации `$key => array()` для полей типа:   ID,   USER\_START\_ID,   SOCNET\_GROUP\_ID,   OWNER\_ID,   FORUM\_ID,   SORT,   POSTS,   TOPICS  перед названием тип проверки фильтра необходимо указывать `@`. Пример:   ``` $topicsDb = CForumTopic::GetList(array("SORT"=>"ASC", "TITLE"=>"NAME";) , array("@FORUM_ID"=>$forumIDs)); while ($arTopic = $topicsDb->Fetch()){ 	$arTopicsIds[] = $arTopic["ID"];Копировать ```    Необязательное. По умолчанию записи не фильтруются. |  |
| bCount | Если параметр равен True, то возвращается только количество тем, которое соответствует установленному фильтру. Необязательный. По умолчанию равен False. |  |
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
	echo htmlspecialcharsbx($ar_res["TITLE"])."<br>";
}
?>Копировать
```

```
<?
// Если нужно выбрать темы по массиву их ID, то пишем перед ID символ "@":
$filter = array("@ID"=>array(10,5,23,111),"APPROVED"=>"Y");
$rs = CForumTopic::GetList(array("SORT"=>"ASC","LAST_POST_DATE"=>"DESC"),$filter);
while($topic = $rs->fetch())
{
	$arResult["TOPICS"][] = $topic;
}
?>Копировать
```

Новинки документации в соцсетях:
[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumNew](/api_help/forum/developer/cforumnew/index.php)

GetListEx (доступен с 3.3.3)

GetListEx
=========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CForumNew::GetList(
	array arOrder = Array("ID"=>"ASC"),
	array arFilter = Array(),
	boolbCount = false,
	intiNum = 0,
	array arAddParams = Array()
);Копировать
```

Возвращает список форумов (включая связанные данные) по фильтру *arFilter*, отсортированный в соответствии с *arOrder*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| arOrder | Массив вида Array(*by1*=>*order1*[, *by2*=>*order2* [, ..]]), где    *by* - поле для сортировки, может принимать значения      **ID** - ID форума;      **LID** - язык форума;      **NAME** - название форума;      **ACTIVE** - активность;      **MODERATION** - модерируемость форума;      **FORUM\_GROUP\_ID** - ID группы форума;      **TOPICS** - количество тем в форуме;      **POSTS** - количество сообщений в форуме;      **LAST\_POST\_DATE** - дата последнего сообщения;      **FORUM\_GROUP\_SORT** - индекс сортировки группы, которой принадлежит форум;      **SORT** - индекс сортировки;    *order* - порядок сортировки, может принимать значения      **ASC** - по возрастанию;      **DESC** - по убыванию;   Необязательный. По умолчанию равен Array("SORT"=>"ASC") |  |
| arFilter | массив вида array("фильтруемое поле"=>"значения фильтра" [, ...]).  Подробное описание параметра смотрите в описании функции [CForumNew::GetList](/api_help/forum/developer/cforumnew/getlist.php). |  |
| bCount | Если параметр равен True, то возвращается только количество форумов, которое соответствует установленному фильтру. Необязательный. По умолчанию равен False. | 11.5.1 |
| iNum | Ограничение числа возвращаемых записей. Если параметр iNum отличен от нуля, то возвращается не более iNum записей. Поддерживается не для всех баз данных. Если параметр не поддерживается, то его установки игнорируются. Необязательный. По умолчанию равен 0. | 11.5.1 |
| arAddParams | Массив параметров. Необязательное. По умолчанию записи не фильтруются. | 11.5.1 |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля форума](/api_help/forum/fields.php#cforumnew)

### Примеры использования

```
<?
// выведем список форумов, к которым текущий посетитель 
// имеет доступ по крайней мере на чтение, 
// сгруппируем список по группам форумов,
// отсортируем список сначала по индексу сортировки, а потом 
// по названию форума
$arFilter = array();
if (!$USER->IsAdmin())
{
	$arFilter["PERMS"] = array($USER->GetGroups(), 'A');
	$arFilter["ACTIVE"] = "Y";
}
$arOrder = array("SORT"=>"ASC", "NAME"=>"ASC");
$db_Forum = CForumNew::GetListEx($arOrder, $arFilter);
$currentGroupID = -1;
while ($db_Forum->NavNext(true, "f_", false)):
	if ($currentGroupID != IntVal($f_FORUM_GROUP_ID))
	{
		if (IntVal($f_FORUM_GROUP_ID)>0)
		{
			$arCurForumGroup = CForumGroup::GetLangByID($f_FORUM_GROUP_ID, LANG);
			echo "<b>";
			echo htmlspecialcharsex($arCurForumGroup["NAME"]);
			echo "<b><br>";
		}
		$currentGroupID = IntVal($f_FORUM_GROUP_ID);
	}
	echo $f_NAME."<br>";
endwhile;
?>Копировать
```

Новинки документации в соцсетях:
[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

GetGroupList (доступен с 3.1.1)

GetGroupList
============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CPosting::GetGroupList(
	int ID
);Копировать
```

Метод возвращает выборку групп пользователей, на которые будет отправлен выпуск. Метод статический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult становятся доступны поля объекта "Группа": ID, NAME.

### Примеры использования

```
<?
//show user groups and check selected for the issue
$aPostGrp = array();
if($ID>0)
{
	$post_grp = CPosting::GetGroupList($ID);
	while($post_grp_arr = $post_grp->Fetch())
		$aPostGrp[] = $post_grp_arr["ID"];
}
$group = CGroup::GetList(($by="name"), ($order="asc"));
while($group->ExtractFields("g_")):
?>
<input type="checkbox" name="GROUP_ID[]" value="<?echo $g_ID?>"<?if(in_array($g_ID, $aPostGrp)) echo " checked"?>>
<?echo $g_NAME?><br>
<?
endwhile;
?>Копировать
```

Новинки документации в соцсетях:
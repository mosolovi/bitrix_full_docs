[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumNew](/api_help/forum/developer/cforumnew/index.php)

GetSites (доступен с 3.3.7)

GetSites
========

```
array
CForumNew::GetSites(
	int ID
);Копировать
```

Функция возвращает ассоциативный массив, в котором ключами являются сайты, к которым привязан форум с кодом ID, а значениями - шаблоны пути к сообщению форума в соответствующем сайте. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код форума. |

#### Примеры использования

```
// Для форума с кодом $FID получим массив реальных путей к сообщению
// с кодом $MID из темы с кодом $TID
$arForumPaths = CForumNew::GetSites($FID);
$arForumPathsCodes = array_keys($arForumPaths);
for ($i = 0; $i < count($arForumPathsCodes); $i++)
{
	$arForumPaths[$arForumPathsCodes[$i]] = 
		CForumNew::PreparePath2Message($arForumPaths[$arForumPathsCodes[$i]],
			array("FORUM_ID"=>$FID,
				"TOPIC_ID"=>$TID,
				"MESSAGE_ID"=>$MID
			)
		);
}Копировать
```

Новинки документации в соцсетях:
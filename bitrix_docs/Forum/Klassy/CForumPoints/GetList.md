[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumPoints](/api_help/forum/developer/cforumpoints/index.php)

GetList (доступен с 3.3.7)

GetList
=======

Включить вкладки

Описание и параметры

Возвращаемые значения

Примеры использования

### Описание и параметры

```
CDBResult
CForumPoints::GetList(
	array arOrder = array("MIN_POINTS"=>"ASC"), 
	array arFilter = array()
);Копировать
```

Возвращает звания форума, которые удовлетворяют фильтру arFilter, упорядоченные в соответствии с порядком arOrder. Метод нестатический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arOrder | Порядок сортировки записей; представляет собой ассоциативный массив, в котором ключами являются названия параметров звания, а значениями - направления сортировки.  Допустимые параметры звания для сортировки:  **ID** - код звания  **CODE** - символьный код   **VOTES** - количество голосов при голосовании  **MIN\_POINTS** - количество баллов, которые нужны для достижения этого звания |
| arFilter | Фильтр на возвращаемые звания; представляет собой ассоциативный массив, в котором ключами являются названия параметров звания, а значениями - условия на эти параметры.  Допустимые параметры звания для фильтрации:  **ID** - код звания  **CODE** - символьный код  **MIN\_POINTS** - количество баллов, которые нужны для достижения этого звания. |

### Возвращаемые значения

Возвращается объект класса CDBResult, каждая запись которого представляет собой массив с ключами

| Ключ | Значение |
| --- | --- |
| ID | Код звания. |
| MIN\_POINTS | Количество баллов, необходимое для получения этого звания. |
| CODE | Символьный код. |
| VOTES | Количество голосов, которое имеет пользователь с этим званием. |

### Примеры использования

```
// Сортировка по количеству голосов по убыванию
// при равном количестве голосов сортировка по ID по возрастанию
$arOrder = array("VOTES"=>"DESC", "ID"=>"ASC");
// Фильтр указывает, что нужно выбирать только те звания
// для получения которых нужно как минимум 50 баллов
$arFilter = array(">=MIN_POINTS"=>50);
$db_res = CForumPoints::GetList($arOrder, $arFilter);
while ($ar_res = $db_res->Fetch())
{
	echo $ar_res["ID"]."-".$ar_res["VOTES"]."<br>";
}Копировать
```

Новинки документации в соцсетях:
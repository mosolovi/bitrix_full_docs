[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUserPoints](/api_help/forum/developer/cforumuserpoints/index.php)

Update (доступно с 3.3.7)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CForumUserPoints::Update(
	int FROM_USER_ID, 
	int TO_USER_ID, 
	array arFields
);Копировать
```

Изменяет параметры голосования пользователя с кодом FROM\_USER\_ID за пользователя с кодом TO\_USER\_ID на значения, указанные в массиве arFields. Метод нестатический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| FROM\_USER\_ID | Пользователь, который голосовал. |  |
| TO\_USER\_ID | Пользователь, за которого голосовали. |  |
| arFields | Массив новых значений параметров голосования. |  |

#### Возвращаемые значения

Возвращает True в случае успешного изменения параметров голосования и False - в противном случае.

### Примеры использования

```
<?
// Изменим количество голосов, отданных текущим пользователем
// за пользователя с кодом $UID на 53
$arFields = array("POINTS" => 53);
if (CForumUserPoints::Update($USER->GetID(), $UID, $arFields))
	echo "Голосования успешно изменено";
else
	echo "Ошибка изменения голосования";
?>Копировать
```

Новинки документации в соцсетях:
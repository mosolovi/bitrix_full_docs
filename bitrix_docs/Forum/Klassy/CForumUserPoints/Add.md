[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUserPoints](/api_help/forum/developer/cforumuserpoints/index.php)

Add (доступно с 3.3.7)

Add
===

```
bool
CForumUserPoints::Add(
	array arFields
);Копировать
```

Функция добавляет новую запись в таблицу голосований за посетителей форума. Метод нестатический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Ассоциативный массив значений параметров записи. |  |

#### Возвращаемые значения

Функция возвращает код добаленной записи или false в случае ошибки.

#### Пример использования

```
<?
// Текущий пользователь отдает пользователю с кодом $UID 10 голосов
$arFields = array(
	"POINTS" => 10,
	"FROM_USER_ID" => $USER->GetID(),
	"TO_USER_ID" => $UID
);
if (CForumUserPoints::Add($arFields))
	echo "Голоса успешно отданы";
else
	echo "Ошибка голосования";
?>Копировать
```

Новинки документации в соцсетях:
[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumNew](/api_help/forum/developer/cforumnew/index.php)

GetByIDEx (доступен с 3.3.3)

GetByIDEx
=========

```
array
GetByIDEx(
	int ID,
	bool SITE_ID = false,
	array arAddParams()
);Копировать
```

Возвращает массив параметров форума, а так же сопутствующие параметры, по его коду *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код форума. |  |
| SITE\_ID | Код сайта. Необязательный. По умолчанию равен False. | 8.0.0 |
| arAddParams | Массив параметров. | 12.0.0 |

#### Возвращаемое значение

Массив параметров форума, включая сопутствующие. Если форум не найден, то возвращается значение false.

#### Смотрите также

* [Поля форума](/api_help/forum/fields.php#cforumnew)

#### Примеры использования

```
<?
// Распечатаем на экран все возвращаемые параметры форума
$arForum = CForumNew::GetByIDEx($FID);
if ($arForum)
{
	echo "<pre>";
	print_r($arForum);
	echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях:
[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumMessage](/api_help/forum/developer/cforummessage/index.php)

GetByID (доступен с 3.3.3)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CForumMessage::GetByID(
	int ID,
	array arAddParams = Array()
);Копировать
```

Возвращает массив параметров сообщения по его коду **ID**. Метод статический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Код сообщения. |  |
| arAddParams | Массив добавления параметров. | 8.0.16 |

#### Возвращаемое значение

Массив параметров сообщения. Если сообщение не найдено, то возвращается значение false.

#### Смотрите также

* [Поля сообщения](/api_help/forum/fields.php#cforummessage)

### Примеры использования

```
<?
$arMessage = CForumMessage::GetByID($MID);
if ($arMessage)
{
	$TID = IntVal($arMessage["TOPIC_ID"]);
	$FID = IntVal($arMessage["FORUM_ID"]);
}
?>Копировать
```

Новинки документации в соцсетях:
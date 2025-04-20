[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumPrivateMessage](/api_help/forum/developer/cforumprivatemessage/index.php)

GetByID (доступен с 4.0.3)

GetByID
=======

```
array
GetByID(
	int ID
);Копировать
```

Возвращает массив параметров сообщения по его коду *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код сообщения. |

#### Возвращаемое значение

Массив параметров сообщения. Если сообщение не найдено, то возвращается значение false.

#### Смотрите также

* таблица ["Приватное сообщение"](/api_help/forum/fields.php#cforumprivatemessage)

#### Примеры использования

```
<?
$arMessage = CForumPrivateMessage::GetByID($MID);
if ($arMessage)
{
	$AUTHOR_ID = IntVal($arMessage["AUTHOR_ID"]);
	$USER_ID = IntVal($arMessage["USER_ID"]);
}
?>Копировать
```

Новинки документации в соцсетях:
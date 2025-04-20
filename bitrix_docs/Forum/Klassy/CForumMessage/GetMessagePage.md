[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumMessage](/api_help/forum/developer/cforummessage/index.php)

GetMessagePage

GetMessagePage
==============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
GetMessagePage(
	int ID,
	int mess_per_page,
	array arUserGroups,
	bool TID = false,
	array arAddParams
);Копировать
```

Возвращает страницу, на которой будет находиться сообщение с кодом *ID* для пользователя, входящего в группы *arUserGroups*, при постраничном показе с *mess\_per\_page* сообщениями на странице. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код сообщения. |  |
| mess\_per\_page | Количество сообщений на страницу. Обычно равно переменной $FORUM\_MESSAGES\_PER\_PAGE, которая определяется модулем форума. Эта переменная инициализируется из настроек модуля форума. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray(). |  |
| TID | Код темы форума. Необязательный. По умолчанию равен False. | 4.0.3 |
| arAddParams | Массив параметров, принимает на вход следующие ключи:  * ORDER\_DIRECTION - сортировка (можно сказать, обратная навигация), принимает значения DESC/ASC. * FILTER - массив, дополнительный фильтр, который накладывается на получение сообщений темы (например, строго определенного автора). * PERMISSION\_EXTERNAL - права доступа. | 7.0.2 |

#### Возвращаемое значение

Номер страницы, на которой будет показано сообщение. Если сообщение не найдено, то возвращается значение false.

### Смотрите также

* [CDBResult::NavStart](/api_help/main/reference/cdbresult/navstart.php)

### Примеры использования

```
<?
if ($MID>0)
	$db_Message->NavStart($FORUM_MESSAGES_PER_PAGE, true, CForumMessage::GetMessagePage($MID, $FORUM_MESSAGES_PER_PAGE, $USER->GetUserGroupArray()));
else
	$db_Message->NavStart($FORUM_MESSAGES_PER_PAGE);
?>Копировать
```

Новинки документации в соцсетях:
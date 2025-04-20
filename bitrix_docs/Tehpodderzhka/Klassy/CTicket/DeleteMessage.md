[Техподдержка](/api_help/support/index.php)

[Классы](/api_help/support/classes/index.php)

[CTicket](/api_help/support/classes/cticket/index.php)

DeleteMessage (3.2.1)

DeleteMessage
=============

```
record set
CTicket::DeleteMessage(
	int MESSAGE_ID,
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод удаляет сообщение. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| **MESSAGE\_ID** | ID сообщения. |  |
| **CHECK\_RIGHTS** | "Y" - необходимо проверить право на удаление у текущего пользователя (по умолчанию); "N" - прав проверять не надо. Необязательный параметр. С версии 12.0.0 изменен на **checkRights**. | 3.3.7 |

Новинки документации в соцсетях:
[Техподдержка](/api_help/support/index.php)

[Классы](/api_help/support/classes/index.php)

[CTicket](/api_help/support/classes/cticket/index.php)

Delete (3.3.7)

Delete
======

```
record set
CTicket::Delete(
	int TICKET_ID,
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод удаляет обращение. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| **TICKET\_ID** | ID обращения. С версии 12.0.0 изменен на **ticketID**. |
| **CHECK\_RIGHTS** | "Y" - необходимо проверить право на удаление у текущего пользователя (по умолчанию); "N" - прав проверять не надо. Необязательный параметр. С версии 12.0.0 изменен на **checkRights**. |

Новинки документации в соцсетях:
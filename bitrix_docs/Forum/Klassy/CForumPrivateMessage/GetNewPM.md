[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumPrivateMessage](/api_help/forum/developer/cforumprivatemessage/index.php)

GetNewPM (доступен с 4.0.3)

GetNewPM
========

```
array
ClassName::GetNewPM(
	bool FOLDER_ID = false
);Копировать
```

Позволяет получить количество непрочитанных персональных сообщений. Метод статический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| FOLDER\_ID | Идентификатор папки. Необязательный. По умолчанию равен False. | 8.0.2 |

#### Возвращаемое значение

Возвращается массив с единственным ключом UNREAD\_PM

Новинки документации в соцсетях:
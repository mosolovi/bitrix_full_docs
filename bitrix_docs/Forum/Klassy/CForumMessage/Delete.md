[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumMessage](/api_help/forum/developer/cforummessage/index.php)

Delete (доступен с 3.3.3)

Delete
======

```
bool
Delete(
	int ID
);Копировать
```

Удаляет сообщение с кодом *ID*.

**Примечание**. Метод использует внутреннюю транзакцию. Если у вас используется **MySQL** и **InnoDB**, и ранее была открыта транзакция, то ее необходимо закрыть до подключения метода. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код сообщения, которое необходимо удалить. |

#### Возвращаемое значение

Возвращает True в случае успешного удаления, в противном случае возвращает False.

Перед удалением вызывает событие onBeforeMessageDelete с параметрами $ID и $arMessage, возвращение false из обработчика отменяет удаление сообщения.

После удаления вызывает событие onAfterMessageDelete с теми же параметрами структура массива $arMessage соответствует результату работы функции CForumMessage::GetByID($ID).

#### Смотрите также

* Перед удалением сообщения следует проверить возможность удаления методом [CForumMessage::CanUserDeleteMessage](/api_help/forum/developer/cforummessage/canuserdeletemessage.php)

Новинки документации в соцсетях:
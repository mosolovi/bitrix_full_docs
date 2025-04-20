[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumTopic](/api_help/forum/developer/cforumtopic/index.php)

Add (доступно с 3.3.3)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
Add(
	array arFields
);Копировать
```

Создает новую тему с параметрами, указанными в массиве *arFields*. Возвращает код созданной темы. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где    *field* - название поля;  *value* - значение поля.   Поля перечислены в [списке полей темы](/api_help/forum/fields.php#cforumtopic). Обязательные поля должны быть заполнены. |  |

#### Возвращаемое значение

Возвращает код созданной темы. В случае ошибки добавления возвращает False.

#### Смотрите также

* [Поля темы](/api_help/forum/fields.php#cforumtopic)
* Перед добавлением темы следует проверить возможность добавления методом [CForumTopic::CanUserAddTopic](/api_help/forum/developer/cforumtopic/canuseraddtopic.php)
* Для добавления и изменения сообщения и темы рекомендуется пользоваться высокоуровневой функцией [ForumAddMessage](/api_help/forum/functions/forumaddmessage.php)

### Примеры использования

```
<?
// для добавления перемещенной темы:
CForumTopic::Add(array('TITLE'=>$title,
	'STATE'=>"L",
	'USER_START_ID'=>$USER->GetID(),
	'USER_START_NAME'=>$USER->GetLogin(),
	'LAST_POSTER_NAME'=>$USER->GetLogin(),
	'START_DATE'=>date("Y-m-d H:i:s",time()),
	'FORUM_ID'=>intval($val),
	'TOPIC_ID'=>$TID,
));
?>Копировать
```

Новинки документации в соцсетях:
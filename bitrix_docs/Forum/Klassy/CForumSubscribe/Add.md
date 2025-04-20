[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumSubscribe](/api_help/forum/developer/cforumsubscribe/index.php)

Add (доступен с 3.3.3)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Пример

### Описание и параметры

```
int
Add(
	array arFields
);Копировать
```

Создает новую запись в таблице подписки с параметрами, указанными в массиве *arFields*. Возвращает код созданной записи. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в [списке полей подписки](/api_help/forum/fields.php#cforumsubscribe). Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Возвращает код созданной записи. В случае ошибки добавления возвращает False.

### Смотрите также

* [Поля подписки](/api_help/forum/fields.php#cforumsubscribe)
* Перед добавлением подписки следует проверить возможность добавления методом [CForumSubscribe::CanUserAddSubscribe](/api_help/forum/developer/cforumsubscribe/canuseraddsubscribe.php)

### Пример

Пример подписки для текущего авторизованного пользователя

```
CForumSubscribe::Add(array( 
	"USER_ID" => $USER->GetID(), 
	"FORUM_ID" => $arParams["FORUM_ID"], 
	"TOPIC_ID" => $arResult["TOPIC_ID"], 
	"SITE_ID" => SITE_ID
));Копировать
```

Новинки документации в соцсетях:
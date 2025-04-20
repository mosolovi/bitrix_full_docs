[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumPrivateMessage](/api_help/forum/developer/cforumprivatemessage/index.php)

Send (доступен с 4.0.3)

Send
====

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int Send(
	array arFields 
);Копировать
```

Создает новое сообщение с параметрами, указанными в массиве *arFields*. Возвращает код созданного сообщения. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в списке полей таблицы ["Приватное сообщение"](/api_help/forum/fields.php#cforumprivatemessage). Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Возвращает код созданного сообщения. В случае ошибки добавления возвращает False.

#### Смотрите также

* таблица ["Приватное сообщение"](/api_help/forum/fields.php#cforumprivatemessage)

### Примеры использования

```
<?
$arFields = Array(
	"AUTHOR_ID"    => $AUTHOR_ID,
	"POST_DATE"    => $POST_DATE,   
	"POST_SUBJ"    => $POST_SUBJ,   
	"POST_MESSAGE" => $POST_MESSAGE,
	"USER_ID"      => $USER_ID,     
	"FOLDER_ID"    => 1,   
	"IS_READ"      => "N",     
	"USE_SMILES"   => ($USE_SMILES=="Y") ? "Y" : "N",
	"AUTHOR_NAME"  => $AUTHOR_NAME 
);
$ID = CForumPrivateMessage::Send($arFields);
if (IntVal($ID)<=0)
	echo "Error!";
?>Копировать
```

Новинки документации в соцсетях:
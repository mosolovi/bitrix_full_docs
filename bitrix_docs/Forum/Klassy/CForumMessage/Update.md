[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumMessage](/api_help/forum/developer/cforummessage/index.php)

Update (доступен с 3.3.3)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
Update(
	int ID,
	array arFields [,
	bool skip_counts [,
	string strUploadDir]]
);Копировать
```

Изменяет параметры существующего сообщения с кодом *ID* на параметры, указанные в массиве *arFields*. Возвращает код изменяемого сообщения. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код сообщения, параметры которого необходимо изменить. |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где    *field* - название поля;  *value* - значение поля.   Поля перечислены в [списке полей сообщения](/api_help/forum/fields.php#cforummessage). |
| skip\_counts | Если этот параметр установлен в значение true, то при изменении сообщения не будут автоматически обсчитаны статистические данные. Это ускоряет работу функции, но создает логические ошибки в данных. Необязательный. По умолчанию равен False. |
| strUploadDir | Каталог для загрузки файлов. Должен быть задан относительно главного каталога для загрузки. Необязательный. По умолчанию равен "forum". |

#### Возвращаемое значение

Возвращает код измененного сообщения. В случае ошибки изменения возвращает False.

#### Примечания

Перед изменением сообщения следует проверить возможность изменения методом [CForumMessage::CanUserUpdateMessage](/api_help/forum/developer/cforummessage/canuserupdatemessage.php).

Для добавления и изменения сообщения и темы рекомендуется пользоваться высокоуровневой функцией [ForumAddMessage](/api_help/forum/functions/forumaddmessage.php).

### Смотрите также

* [Поля сообщения](/api_help/forum/fields.php#cforummessage)

### Примеры использования

```
// Добавление информации о редактировании на форумах, где есть только логины: 
// 1. Не стоит использовать время PHP (время PHP и БД довольно часто различается, а сейчас в форуме, практически, везде используется время БД);
// 2. Нельзя показывать логин пользователя без его разрешения.
<?
$arUser = CForumUser::GetByUSER_ID($USER->GetID());
$arFields = array( 
	"POST_MESSAGE" => $_POST["POST_MESSAGE"], 
	"EDIT_DATE" => "", 
	"EDITOR_ID" => $USER->GetID(), 
	"EDITOR_NAME" => trim($arUser["SHOW_NAME"] == "Y" ? $USER->GetFullName() : $USER->GetLogin())
);
$arFields["EDITOR_NAME"] = (empty($arFields["EDITOR_NAME"]) ? $USER->GetLogin() : $arFields["EDITOR_NAME"]);
CForumMessage::Update($MID, $arFields);
?>Копировать
```

Новинки документации в соцсетях:
[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumMessage](/api_help/forum/developer/cforummessage/index.php)

Add (доступен с 3.3.3)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CForumMessage::Add(
	array arFields = Array(),
	string strUploadDir = false,
	array arParams = Array()
);Копировать
```

Создает новое сообщение с параметрами, указанными в массиве *arFields*. Возвращает код созданного сообщения. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где  * **field** - название поля; * **value** - значение поля.  Поля перечислены в [списке полей сообщения](/api_help/forum/fields.php#cforummessage). Обязательные поля должны быть заполнены.    Для первого сообщения в теме форума - обязательно передать параметр "NEW\_TOPIC" => "Y". |  |
| strUploadDir | Каталог для загрузки файлов. Должен быть задан относительно главного каталога для загрузки. Необязательный. По умолчанию равен "forum". |  |
| arParams | Массив параметров. Необязательный. | 7.0.0 |

#### Возвращаемое значение

Возвращает код созданного сообщения. В случае ошибки добавления возвращает **False**.

#### Примечания

Перед добавлением сообщения следует проверить возможность добавления методом [CForumMessage::CanUserAddMessage](/api_help/forum/developer/cforummessage/canuseraddmessage.php).

Для добавления и изменения сообщения и темы рекомендуется пользоваться высокоуровневой функцией [ForumAddMessage](/api_help/forum/functions/forumaddmessage.php).

### Смотрите также

* [Поля сообщения](/api_help/forum/fields.php#cforummessage)

### Примеры использования

#### Пример 1

```
<?
$arFields = Array(
	"POST_MESSAGE" => $POST_MESSAGE,
	"USE_SMILES" => ($USE_SMILES=="Y") ? "Y" : "N",
	"APPROVED" => $APPROVED,
	"AUTHOR_NAME" => $AUTHOR_NAME,
	"AUTHOR_ID" => $AUTHOR_ID,
	"FORUM_ID" => $FID,
	"TOPIC_ID" => $TID,
	"AUTHOR_IP" => ($AUTHOR_IP!==False) ? $AUTHOR_IP : "",
	"NEW_TOPIC" => "N"
);
$ID = CForumMessage::Add($arFields);
if (IntVal($ID)<=0)
	echo "Error!";
?>Копировать
```

  

#### Пример 2

Если необходимо узнать ошибку:

```
<?
$arFields = Array(
	"POST_MESSAGE" => $POST_MESSAGE,
	"USE_SMILES" => ($USE_SMILES=="Y") ? "Y" : "N",
	"APPROVED" => $APPROVED,
	"AUTHOR_NAME" => $AUTHOR_NAME,
	"AUTHOR_ID" => $AUTHOR_ID,
	"FORUM_ID" => $FID,
	"TOPIC_ID" => $TID,
	"AUTHOR_IP" => ($AUTHOR_IP!==False) ? $AUTHOR_IP : "",
	"NEW_TOPIC" => "N"
);
$ID = CForumMessage::Add($arFields);
if ($ID<=0 && $ex=$APPLICATION->GetException())
	echo $ex->GetString();
?>Копировать
```

  

#### Пример 3

IP адрес проходит дополнительную проверку и, если он отличается от реального IP адреса пользователя, то на форуме вместо:

**IP: ###.###.###.###**

выводится:

**IP / реальный: ###.###.###.### /** 

Для того, чтобы этого избежать, используем дополнительное поле:

```
"AUTHOR_IP" => $AUTHOR_IP,
"AUTHOR_REAL_IP"=> $AUTHOR_IP,Копировать
```

Новинки документации в соцсетях:
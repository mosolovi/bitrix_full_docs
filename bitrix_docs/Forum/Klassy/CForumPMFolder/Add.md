[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumPMFolder](/api_help/forum/developer/cforumpmfolder/index.php)

Add (доступен с 4.0.3)

Add
===

```
int Add(
	string Title 
);Копировать
```

Создает новую папку с названием, указанным в *Title*. Возвращает код созданной папки. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| Title | Название папки. Обязательный параметр. |

#### Возвращаемое значение

Возвращает код созданного сообщения. В случае ошибки добавления возвращает False.

#### Смотрите также

* таблица ["Папка пользователя"](/api_help/forum/fields.php#cforumpmfolder)

#### Примеры использования

```
<?
$ID = CForumPMFolder::Add($TITLE);
if (IntVal($ID)<=0)
	echo "Error!";
?>Копировать
```

Новинки документации в соцсетях:
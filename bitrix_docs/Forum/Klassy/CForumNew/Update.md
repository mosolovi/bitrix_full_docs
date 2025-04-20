[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumNew](/api_help/forum/developer/cforumnew/index.php)

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
	array arFields,
	bool bReindex = true
);Копировать
```

Изменяет параметры существующего форума с кодом *ID* на параметры, указанные в массиве *arFields*. Возвращает код изменяемого форума. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код форума, параметры которого необходимо изменить. |  |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где    *field* - название поля;  *value* - значение поля.   Поля перечислены в [списке полей форума](/api_help/forum/fields.php#cforumnew). |  |
| bReindex | Необязательный. По умолчанию равен True. | 10.0.2 |

#### Возвращаемое значение

Возвращает код измененного форума. В случае ошибки изменения возвращает False.

### Смотрите также

* [Поля форума](/api_help/forum/fields.php#cforumnew)
* Перед изменением форума следует проверить возможность изменения методом [CanUserUpdateForum](/api_help/forum/developer/cforumnew/canuserupdateforum.php)

### Примеры использования

```
<?
// Этот код привязывает сайт с кодом $site_code к форуму $FORUM_ID и прописывает "Шаблон пути к сообщению на сайте" в виде $FORUM_PATH
$arFields = array("ACTIVE" => "Y", "SITES" => CForumNew::GetSites($FORUM_ID));
$arFields["SITES"][$site_code] = str_replace("#SITE_PATH#", $site_path, $FORUM_PATH);
CForumNew::Update($FORUM_ID, $arFields);
?>Копировать
```

Новинки документации в соцсетях:
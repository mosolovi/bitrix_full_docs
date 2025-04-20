[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUserGroup](/api_help/blogs/classes/cblogusergroup/index.php)

Add (7.1.2)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CBlogUserGroup::Add(
	array arFields
);Копировать
```

Метод добавляет новую группу пользователей блога. Метод нестатический.

**Примечание:** при установке модуля автоматически создаются две группы пользователей блога, которые доступны для всех блогов: "Все посетители" и "Авторизованные посетители". Следующая группа уже будет привязана к конкретному блогу и будет иметь ID, равный 3.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида *array("поле"=>"значение"[, ...])*, содержащий значения [полей группы пользователей блога](/api_help/blogs/fields.php#usergroup). |

#### Возвращаемое значение

Метод возвращает идентификатор добавленной группы пользователей, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [CBlogUserGroup](/api_help/blogs/classes/cblogusergroup/index.php)::[Update](/api_help/blogs/classes/cblogusergroup/update.php)
* [Поля группы пользователей](/api_help/blogs/fields.php#post)

### Примеры использования

```
<?
$arFields = array(
	"NAME" => 'Друзья',
	"BLOG_ID" => 1
);
$newID = CBlogUserGroup::Add($arFields);
if(IntVal($newID)>0)
{
	echo "Новая группа [".$newID."] добавлена.";
}
else
{
	if ($ex = $APPLICATION->GetException())
		echo $ex->GetString();
}
?>Копировать
```

Новинки документации в соцсетях:
[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUser](/api_help/blogs/classes/cbloguser/index.php)

GetUserName (5.0.2)

GetUserName
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
string
CBlogUser::GetUserName(
	string alias,
	string name,
	string lastName,
	string login
);Копировать
```

Метод возвращает имя пользователя в зависимости от наличия параметров и разрешения использовать псевдоним. Если разрешен псевдоним, то вернется псевдоним, если нет, но есть имя или фамилия, то вернется имя и фамилия, в противном случае просто логин пользователя сайта. Метод статический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| alias | Псевдоним пользователя блога. |  |
| name | Имя пользователя сайта. |  |
| lastName | Фамилия пользователя сайта. |  |
| login | Логин пользователя сайта. |  |
| secondName | Необязательный параметр. Значение по умолчанию - "". | 12.0.0 |

#### Возвращаемое значение

Возвращается имя пользователя.

### Примеры использования

```
<?
//выведем имя текущего пользователя для блогов
$dbUser = CUser::GetByID($USER->GetID());
$arUser = $dbUser->Fetch();
$BlogUser = CBlogUser::GetByID($arUser["ID"], BLOG_BY_USER_ID); 
$AuthorName = CBlogUser::GetUserName($BlogUser["ALIAS"], $arUser["NAME"], $arUser["LAST_NAME"], $arUser["LOGIN"]);
echo $AuthorName;
?>Копировать
```

Новинки документации в соцсетях:
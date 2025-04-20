[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUser](/api_help/blogs/classes/cbloguser/index.php)

GetUserFriends (5.0.2)

GetUserFriends
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CBlogUser::GetUserFriends(
	int  ID,
	bool bFlag = true
);Копировать
```

В зависимости от флага *bFlag* возвращает или список блогов друзей пользователя *ID* или список блогов, в которых пользователь *ID* является другом. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор пользователя сайта. |
| bFlag | Флаг. Если значение **true**, то возвращается список блогов в которых пользователь является другом, в противном случае возвращается список блогов друзей пользователя. Необязательный. По умолчанию **true** - возвращается список блогов в которых пользователь является другом. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Примеры использования

```
<?
// выберем все блоги друзей пользователя
$dbFriends = CBlogUser::GetUserFriends($USER->GetID(), True);
while ($arFriends = $dbFriends->Fetch())
{
	?><a href="<?= CBlog::PreparePath($arFriends["URL"], false, $is404) ?>"><?= htmlspecialchars($arFriends["NAME"]) ?></a><?
}
?>Копировать
```

Новинки документации в соцсетях:
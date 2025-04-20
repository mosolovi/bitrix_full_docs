[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogPost](/api_help/blogs/classes/cblogpost/index.php)

SetPostPerms (5.0.2)

SetPostPerms
============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
void
CBlogPost::SetPostPerms(
	int    ID,
	array  arPerms,
	string permsType = BLOG_PERMS_POST
);Копировать
```

Метод устанавливает уровень доступа к сообщению и комментариям сообщения *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сообщения. |
| arPerms | Массив вида: *array("BlogUserGroupID" => "Permissions"[, ...])*, где   *BlogUserGroupID* - идентификатор группы пользователей текущего блога,  *Permissions* - уровень доступа. Необязательный параметр. |
| permsType | Тип уровня доступа, который необходимо установить. Возможные значения:  * **BLOG\_PERMS\_POST** - на сообщение; * **BLOG\_PERMS\_COMMENT** - на комментарии к сообщению.  Необязательный. По умолчанию равен *BLOG\_PERMS\_POST* - будет изменен уровень доступа к сообщению. |

### Смотрите также

* [Уровни доступа к сообщениям блога](/api_help/blogs/constant.php#pperms)
* [Уровни доступа к комментариям блога](/api_help/blogs/constant.php#)

### Примеры использования

```
<?
$ID = 1;
$arPerms = Array(
	"1" => BLOG_PERMS_READ,
	"2" => BLOG_PERMS_WRITE
);
CBlogPost::SetPostPerms($ID, $arPerms, BLOG_PERMS_COMMENT);
?>Копировать
```

Новинки документации в соцсетях:
[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumNew](/api_help/forum/developer/cforumnew/index.php)

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
CForumNew::Add(
	array arFields
);Копировать
```

Создает новый форум с параметрами, указанными в массиве *arFields*. Возвращает код созданного форума. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в [списке полей форума](/api_help/forum/fields.php#cforumnew). Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Возвращает код созданного форума. В случае ошибки добавления возвращает False.
  
  
Параметр GROUP\_ID задает права доступа группам пользователей к создаваемому форуму. Ключ массива - ID группы пользователей, значение - один из следующих вариантов:   
A - нет доступа   
E - чтение   
I - ответ   
M - новая тема   
Q - модерирование   
U - редактирование   
Y - полный доступ.

### Смотрите также

* [Поля форума](/api_help/forum/fields.php#cforumnew)
* Перед добавлением форума следует проверить возможность добавления методом [CForumNew::CanUserAddForum](/api_help/forum/developer/cforumnew/canuseraddforum.php)

### Примеры использования

```
<?
CModule::IncludeModule("forum");
$arFields = Array(
	"NAME" => "Название форума", 
	"DESCRIPTION" => "Описание форума (м.б. пустым, м.б. html-код)",
	"FORUM_GROUP_ID" => 0,
	"GROUP_ID" => array(1 => "Y", 2 => "I"), 
	"SITES" => array(), // заполняется ниже
	"ACTIVE" => "Y", 
	"MODERATION" => "N",
	"INDEXATION" => "Y",
	"SORT" => 150,
	"ASK_GUEST_EMAIL" => "N",
	"USE_CAPTCHA" => "N",
	"ALLOW_HTML" => "N",
	"ALLOW_ANCHOR" => "Y",
	"ALLOW_BIU" => "Y",
	"ALLOW_IMG" => "Y",
	"ALLOW_VIDEO" => "Y",
	"ALLOW_LIST" => "Y",
	"ALLOW_QUOTE" => "Y",
	"ALLOW_CODE" => "Y",
	"ALLOW_FONT" => "Y",
	"ALLOW_SMILES" => "Y",
	"ALLOW_UPLOAD" => "Y", 
	"ALLOW_UPLOAD_EXT" => "",
	"ALLOW_TOPIC_TITLED" => "N", 
	"EVENT1" => "forum"
);
   
$db_res = CSite::GetList($lby="sort", $lorder="asc");
while ($res = $db_res->Fetch()):
	$arFields["SITES"][$res["LID"]] = "/".$res["LID"]."/forum/#FORUM_ID#/#TOPIC_ID#/";
endwhile;
$res = CForumNew::Add($arFields);
if (intVal($res) > 0):
	echo "New Forum ID: ".$res;
else:
	$e = $GLOBALS['APPLICATION']->GetException();
	if ($e && $str = $e->GetString()):
		echo "Error: ".$str;
	else:
		echo "Unknown Error";
	endif;
endif;
?>
Короткий пример добавления форума c обязательными полями:
 
<?
CModule::IncludeModule("forum");
$arFields = Array(
	"NAME" => "Имя форума",
	"GROUP_ID" => array(1 => "Y", 2 => "I"), 
	"SITES" => array(
		"ru" => "/url/"
	)
);
$res = CForumNew::Add($arFields);
?>Копировать
```

Новинки документации в соцсетях:
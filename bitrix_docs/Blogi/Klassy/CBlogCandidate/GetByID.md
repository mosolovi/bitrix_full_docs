[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogCandidate](/api_help/blogs/classes/cblogcandidate/index.php)

GetByID (7.1.2)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CBlogCandidate::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры записи с идентификатором *ID*. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор записи. |

#### Возвращаемое значение

Возвращается массив вида:

```
Array(
	"ID"=>"ID записи",
	"BLOG_ID"=>"ID блога",
	"USER_ID"=>"ID пользователя"
)Копировать
```

#### Примечание

Метод использует встроенное кэширование. Таким образом, запрос к базе данных при многократном использовании метода на странице будет производиться только один раз.

### Смотрите также

* [CBlogCandidate](/api_help/blogs/classes/cblogcandidate/index.php)::[GetList()](/api_help/blogs/classes/cblogcandidate/getlist.php)

### Примеры использования

```
<?
$ID = 1;
$arCandidate = CBlogCandidate::GetByID($ID);
if(is_array($arCandidate))
	print_r($arCandidate);
else
	echo "Запись не найдена";
?>Копировать
```

Новинки документации в соцсетях:
[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumTopic](/api_help/forum/developer/cforumtopic/index.php)

GetByIDEx (доступно с 3.3.3)

GetByIDEx
=========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
array
CForumTopic::GetByIDEx(
	int ID,
	array arAddParams = Array()
);Копировать
```

Возвращает массив параметров темы, а так же сопутствующие параметры, по ее коду *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код темы. |  |
| arAddParams | Массив параметров. | 4.0.3 |

#### Возвращаемое значение

Массив параметров темы, включая сопутствующие. Если тема не найдена, то возвращается значение false.

#### Смотрите также

* [Поля темы](/api_help/forum/fields.php#cforumtopic)

### Примеры использования

```
<?
// Распечатаем на экран все возвращаемые параметры темы
$arTopic = CForumTopic::GetByIDEx($TID);
if ($arTopic)
{
	echo "<pre>";
	print_r($arTopic);
	echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях:
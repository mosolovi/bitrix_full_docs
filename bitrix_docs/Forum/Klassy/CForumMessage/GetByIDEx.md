[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumMessage](/api_help/forum/developer/cforummessage/index.php)

GetByIDEx (доступен с 3.3.3)

GetByIDEx
=========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CForumMessage::GetByIDEx(
	int ID,
	array arAddParams = Array()
);Копировать
```

Возвращает массив параметров сообщения, а так же сопутствующие параметры, по его коду *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Код сообщения. |  |
| arAddParams | Массив добавления параметров. | 8.0.16 |

#### Возвращаемое значение

Массив параметров сообщения, включая сопутствующие. Если сообщение не найдено, то возвращается значение false.

#### Смотрите также

* [Поля сообщения](/api_help/forum/fields.php#cforummessage)

### Примеры использования

```
<?
// Распечатаем на экран все возвращаемые параметры сообщения
$arMessage = CForumMessage::GetByIDEx($MID);
if ($arMessage)
{
	echo "<pre>";
	print_r($arMessage);
	echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях:
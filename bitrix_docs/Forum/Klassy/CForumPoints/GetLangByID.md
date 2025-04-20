[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumPoints](/api_help/forum/developer/cforumpoints/index.php)

GetLangByID (доступен с 3.3.7)

GetLangByID
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
array
CForumPoints::GetLangByID(
	int POINTS_ID, 
	string strLang
);Копировать
```

Возвращает массив языкозависимых параметров звания (рейтинга) форума по его коду. Метод нестатический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| POINTS\_ID | Код звания. |
| strLang | Код языка. |

#### Возвращаемые значения

Возвращает ассоциативный массив с ключами.

| Ключ | Значение |
| --- | --- |
| POINTS\_ID | Код звания. |
| LID | Код языка. |
| NAME | Название звания на языке LID. |

### Примеры использования

```
<?
$ar_res = CForumPoints::GetLangByID(3, "ru");
echo "Звание с кодом ".$ar_res["POINTS_ID"]." на русском языке называется ".$ar_res["NAME"]."";
?>Копировать
```

Новинки документации в соцсетях:
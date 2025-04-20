[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvContract](/api_help/advertising/classes/cadvcontract/index.php)

GetByID (3.3.4)

GetByID
=======

Включить вкладки

Описание и параметры

Пример

### Описание и параметры

```
record set
CAdvContract::GetByID( 
	int CONTRACT_ID,
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод возвращает контракт по его ID. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| CONTRACT\_ID | ID контракта. |
| CHECK\_RIGHTS | Параметр проверяет уровень доступа к модулю Реклама (администратор рекламы, рекламодатель и т.д.). Если параметр определён как "N", то считается, что текущий пользователь обладает административными правами доступа к модулю Реклама. Если параметр пропущен либо равен "Y", то метод проверяет уровень доступа к контракту, которому принадлежит баннер. Необязательный параметр. |

### Пример

#### Пример массива, получаемого после Fetch результата, возвращенного данному методу

```
<?
Array
(
	[LAMP] => green
	[ID] => 3
	[ACTIVE] => Y
	[NAME] => заголовок контракта
	[DESCRIPTION] => описание контракта
	[ADMIN_COMMENTS] => административный комментарий
	[WEIGHT] => 1000
	[SORT] => 200
	[MAX_SHOW_COUNT] => 1000
	[SHOW_COUNT] => 312
	[MAX_CLICK_COUNT] => 100
	[CLICK_COUNT] => 64
	[EMAIL_COUNT] => 0
	[CREATED_BY] => 2
	[MODIFIED_BY] => 2
	[DEFAULT_STATUS_SID] => READY
	[CTR] => 20.51
	[DATE_SHOW_FROM] => 15.06.2004
	[DATE_SHOW_TO] => 07.07.2009
	[DATE_CREATE] => 07.06.2004 19:04:55
	[DATE_MODIFY] => 24.06.2004 10:56:08
	[BANNER_COUNT] => 12
)
?>Копировать
```

Новинки документации в соцсетях:
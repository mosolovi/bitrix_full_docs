[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWikiSocnet](/api_help/wiki/classes/cwikisocnet/index.php)

Init (9.5.1)

Init
====

```
bool
CWikiSocnet::Init(
	int SOCNET_GROUP_ID,
	int IBLOCK_ID
);Копировать
```

Метод инициализирует интеграцию. Статический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| SOCNET\_GROUP\_ID | Идентификатор рабочей группы соц. сети |
| IBLOCK\_ID | Идентификатор инфо.блока |

#### Примеры использования

```
<?
// Инициализируем интеграцию
$SOCNET_GROUP_ID = 14;
$IBLOCK_ID = 3;
if (!CWikiSocnet::Init($SOCNET_GROUP_ID, $IBLOCK_ID))
	echo 'Ошибка. Не удалось инициализировать интеграцию.';
?>Копировать
```

Новинки документации в соцсетях:
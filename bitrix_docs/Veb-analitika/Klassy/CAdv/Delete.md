[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CAdv](/api_help/statistic/classes/cadv/index.php)

Delete

Delete
======

```
bool
CAdv::Delete(
	int adv_id
)Копировать
```

Удаляет [рекламную кампанию](/api_help/statistic/terms.php#adv).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *adv\_id* | ID рекламной кампании. |

#### Смотрите также

* [Термин "Рекламная кампания"](/api_help/statistic/terms.php#adv)
* [CAdv::Reset](/api_help/statistic/classes/cadv/reset.php)

#### Примеры использования

```
<?
$adv_id = 1;
if (CAdv::Delete($adv_id)) 
	echo "Рекламная кампания #".$adv_id." успешно удалена.";
?>Копировать
```

Новинки документации в соцсетях:
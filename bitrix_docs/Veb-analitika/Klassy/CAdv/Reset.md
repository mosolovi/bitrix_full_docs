[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CAdv](/api_help/statistic/classes/cadv/index.php)

Reset

Reset
=====

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CAdv::Reset(
	int adv_id
)Копировать
```

Обнуляет статистические данные [рекламной кампании](/api_help/statistic/terms.php#adv).

**Примечание**. Метод использует внутреннюю транзакцию. Если у вас используется **MySQL** и **InnoDB**, и ранее была открыта транзакция, то ее необходимо закрыть до подключения метода.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *adv\_id* | ID рекламной кампании. |

#### Смотрите также

* [Термин "Рекламная кампания"](/api_help/statistic/terms.php#adv)
* [CAdv::Delete](/api_help/statistic/classes/cadv/delete.php)

### Примеры использования

```
<?
$adv_id = 1;
if (CAdv::Reset($adv_id)) 
	echo "Данные по рекламной кампании #".$adv_id." успешно удалены.";
?>Копировать
```

Новинки документации в соцсетях:
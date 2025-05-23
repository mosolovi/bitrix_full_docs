[Валюты](/api_help/currency/index.php)

[Классы](/api_help/currency/developer/index.php)

[CCurrencyRates](/api_help/currency/developer/ccurrencyrates/index.php)

GetList (3.3.2)

GetList
=======

Включить вкладки

Описание и параметры

Возвращаемые значения

Пример использования

### Описание и параметры

```
CDBResult
CCurrencyRates::GetList(
	string &by, 
	string &order, 
	array arFilter = Array()
);Копировать
```

Метод возвращает список курсов валют, удовлетворяющих фильтру arFilter, отсортированный по полю by в направлении order. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| by | Переменная , содержащая название поля для сортировки. Доступные названия:  date - дата курса (по умолчанию)   curr - валюта  rate - курс. |
| order | Переменная, содержащая направление сортировки. Допустимы значения:  asc - по возрастанию (по умолчанию)  desc - по убыванию. |
| arFilter | Фильтр на записи представляет собой ассоциативный массив, в котором ключами являются названия фильтруемых полей, а значениями - условия фильтра. Необязательный параметр.  Допустимые поля для фильтра:  CURRENCY - код валюты  DATE\_RATE - дата курса (выбираются записи с датами больше или равными указанной)   !DATE\_RATE - дата курса (выбираются записи с датами меньше указанной) |

### Возвращаемые значения

Объект класса CDBResult, содержащий записи с ключами

| Ключ | Описание |
| --- | --- |
| ID | Код курса. |
| CURRENCY | Код валюты. |
| DATE\_RATE | Дата, за которую установлен курс. |
| RATE\_CNT | количество единиц валюты, которое участвует в задании курса валюты (например, если 10 Датских крон стоят 48.7 рублей, то 10 - это количество единиц) |
| RATE | курс валюты (одна из валют сайта должна иметь курс "по-умолчанию" 1, она называется базовой, остальные валюты имеют курс относительно базовой валюты) |

### Пример использования

```

<?
// Выведем все курсы USD, отсортированные по дате
$arFilter = array(
	"CURRENCY" => "USD"
);
$by = "date";
$order = "desc";
$db_rate = CCurrencyRates::GetList($by, $order, $arFilter);
while($ar_rate = $db_rate->Fetch())
{
	echo $ar_rate["RATE"]."<br>";
}
?>Копировать
```

Новинки документации в соцсетях:
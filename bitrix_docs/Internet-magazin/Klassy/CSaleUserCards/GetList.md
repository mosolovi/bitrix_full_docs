[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleUserCards](/api_help/sale/classes/csaleusercards/index.php)

GetList (доступен с 4.0.6)

GetList
=======

Включить вкладки

Описание и параметры

Возвращаемые значения

### Описание и параметры

```
CDBResult
CSaleUserCards::GetList(
	array arOrder = array(),
	array arFilter = array(),
	array arGroupBy = false,
	array arNavStartParams = false,
	array arSelectFields = array()
);Копировать
```

Метод возвращает результат выборки записей пластиковых карт в соответствии со своими параметрами. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arOrder | Массив, в соответствии с которым сортируются результирующие записи. Массив имеет вид:  ``` array( 	"название_поля1" => "направление_сортировки1", 	"название_поля2" => "направление_сортировки2", 	. . . )Копировать ```  В качестве "название\_поля*N*" может стоять любое поле карт, а в качестве "направление\_сортировки*X*" могут быть значения "*ASC*" (по возрастанию) и "*DESC*" (по убыванию).    Если массив сортировки имеет несколько элементов, то результирующий набор сортируется последовательно по каждому элементу (т.е. сначала сортируется по первому элементу, потом результат сортируется по второму и т.д.).     Значение по умолчанию - пустой массив array() - означает, что результат отсортирован не будет. |
| arFilter | Массив, в соответствии с которым фильтруются записи карт. Массив имеет вид:  ``` array( 	"[модификатор1][оператор1]название_поля1" => "значение1", 	"[модификатор2][оператор2]название_поля2" => "значение2", 	. . . )Копировать ```  Удовлетворяющие фильтру записи возвращаются в результате, а записи, которые не удовлетворяют условиям фильтра, отбрасываются.    Допустимыми являются следующие модификаторы:  * **!** - отрицание; * **+** - значения null, 0 и пустая строка так же удовлетворяют условиям фильтра.  Допустимыми являются следующие операторы:  * **>=** - значение поля больше или равно передаваемой в фильтр величины; * **>** - значение поля строго больше передаваемой в фильтр величины; * **>=** - значение поля меньше или равно передаваемой в фильтр величины; * **>=** - значение поля строго меньше передаваемой в фильтр величины; * **@** - значение поля находится в передаваемом в фильтр разделенном запятой списке значений; * **~** - значение поля проверяется на соответствие передаваемому в фильтр шаблону; * **%** - значение поля проверяется на соответствие передаваемой в фильтр строке в соответствии с языком запросов.  В качестве "название\_поляX" может стоять любое поле карт.    Пример фильтра:  ``` array( 	"USER_ID" => 150 )Копировать ```  Этот фильтр означает "выбрать все записи, в которых значение в поле USER\_ID (код пользователя) равно 150".    Значение по умолчанию - пустой массив array() - означает, что результат отфильтрован не будет. |
| arGroupBy | Массив полей, по которым группируются записи карт. Массив имеет вид:  ``` array( 	"название_поля1",  	"группирующая_функция2" => "название_поля2",  	. . . )Копировать ```  В качестве "название\_поля*N*" может стоять любое поле карт. В качестве группирующей функции могут стоять:  * **COUNT** - подсчет количества; * **AVG** - вычисление среднего значения; * **MIN** - вычисление минимального значения; * **MAX** - вычисление максимального значения; * **SUM** - вычисление суммы.  Если массив пустой, то метод вернет число записей, удовлетворяющих фильтру.    Значение по умолчанию - *false* - означает, что результат группироваться не будет. |
| arNavStartParams | Массив параметров выборки. Может содержать следующие ключи:  * "**nTopCount**" - количество возвращаемых методом записей будет ограничено сверху значением этого ключа; * любой ключ, принимаемый методом  **CDBResult::NavQuery**   в качестве третьего параметра.  Значение по умолчанию - *false* - означает, что параметров выборки нет. |
| arSelectFields | Массив полей записей, которые будут возвращены методом. Можно указать только те поля, которые необходимы. Если в массиве присутствует значение "\*", то будут возвращены все доступные поля.    Значение по умолчанию - пустой массив array() - означает, что будут возвращены все поля основной таблицы запроса. |

### Возвращаемые значения

Возвращается объект класса CDBResult, содержащий набор ассоциативных массивов параметров карт.

* **ID** - код пластиковой карты;
* **USER\_ID** - код пользователя;
* **SORT** - индекс сортировки;
* **PAY\_SYSTEM\_ACTION\_ID** - код обработчика платежной системы;
* **CURRENCY** - валюта, которую можно снимать с карты;
* **CARD\_CODE** - CVC2;
* **CARD\_TYPE** - тип карты;
* **CARD\_NUM** - номер карты;
* **CARD\_EXP\_MONTH** - месяц окончания действия карты;
* **CARD\_EXP\_YEAR** - год окончания действия карты;
* **DESCRIPTION** - краткое описание;
* **SUM\_MIN** - минимальная сумма, которую можно снять с карты за раз;
* **SUM\_MAX** - максимальная сумма, которую можно снять с карты за раз;
* **SUM\_CURRENCY** - валюта минимальной и максимальной сумм;
* **LAST\_STATUS** - статус последнего использования карты;
* **LAST\_STATUS\_CODE** - код статуса последнего использования карты;
* **LAST\_STATUS\_DESCRIPTION** - описание статуса последнего использования карты;
* **LAST\_STATUS\_MESSAGE** - сообщение платежной системы;
* **LAST\_SUM** - последняя снятая с карты сумма;
* **LAST\_CURRENCY** - валюта последней снятой с карты суммы;
* **ACTIVE** - флаг активности;
* **TIMESTAMP\_X** - дата изменения;
* **LAST\_DATE** - дата последнего использования карты.

Если в качестве параметра arGroupBy передается пустой массив, то метод вернет число записей, удовлетворяющих фильтру.

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[Функции](/api_help/iblock/functions/index.php)

GetIBlockSectionList (доступна с 3.0.5)

GetIBlockSectionList
====================

Включить вкладки

Описание

Параметры функции

Смотрите также

Примеры использования

### Описание

```
CDBResult
GetIBlockSectionList (
	int iblock_id, 
	int section_id = false, 
	array order = Array("LEFT_MARGIN"=>"ASC"), 
	int cnt = 0, 
	array arFilter = Array() 
);Копировать
```

Функция возвращает активные разделы из информационного блока *iblock\_id*. Использует метод [CIBlockSection::GetList](/api_help/iblock/classes/ciblocksection/getlist.php)

#### Возвращаемое значение

Функция возвращает объект класса [CDBResult](/api_help/main/reference/cdbresult/index.php) с активными разделами (находящиеся в активных информационных блоках (у которых установлен флаг "Активен"), и которые лежат внутри активных разделов).

**Примечания:**

1. При работе с результатом рекомендуется применять метод класса [CDBResult](/api_help/main/reference/cdbresult/index.php)::[GetNext()](/api_help/main/reference/cdbresult/getnext.php), результатом которого будет массив с полями раздела. Все поля при этом будут преобразованы в "HTML безопасный" вид. Если результат пуст или достигнут конец выборки [CDBResult](/api_help/main/reference/cdbresult/index.php)::[GetNext()](/api_help/main/reference/cdbresult/getnext.php) функция вернет false.

2. Поле для сортировки *left\_margin*, так называемая "сквозная" сортировка, высчитывается на основании поля *sort*, уровня вложенности и сортировкой верхнего уровня. Отличие полей *sort* и *left\_margin* в том, что *sort* указывается пользователем, для сортировки разделов между собой в пределах одного раздела-родителя, а вычисляемое *left\_margin* предназначено для сортировки во всем информационном блоке.

### Параметры функции

| Параметр | Описание |
| --- | --- |
| iblock\_id | ID информационного блока из которого будут выбраны разделы. |
| section\_id | ID папки-родителя. Для получения корневых разделов информационного блока установите параметр *section\_id* = 0.   Необязательный. По умолчанию (false) выбираются все записи без ограничения по разделу-родителю. |
| order | Массив вида Array(*order1*=>*by1*[, *order2*=>*by2* [, ..]]), где *order* - поле для сортировки, может принимать значения:  * **sort** - индекс сортировки; * **timestamp\_x** - дата изменения; * **name** - название; * **id** - ID папки; * **left\_margin** - поле обозначающее "сквозную" сортировку (см. Примечание); * **depth\_level** - уровень вложенности папки; * **by** - порядок сортировки сортировки, может принимать значения:   + **asc** - по возрастанию;   + **desc** - по убыванию.Необязательный. По умолчанию равен *Array("left\_margin"=>"asc")*.  Полный список полей сортировки и дополнительную информацию [смотрите](/api_help/iblock/classes/ciblocksection/getlist.php) в [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)::[GetList()](/api_help/iblock/classes/ciblocksection/getlist.php) |
| cnt | Максимальное количество записей, которые вернет функция.   Необязательный. По умолчанию выбираются все записи. |
| arFilter | Дополнительный фильтр - массив вида array("фильтруемое поле"=>"значение" [, ...])   Может принимать значения:  * **ACTIVE** - фильтр по активности (Y|N); * **GLOBAL\_ACTIVE** - фильтр по активности, учитывая активность вышележащих разделов (Y|N); * **NAME** - по названию (можно искать по шаблону [%\_]); * **CODE** - по символьному коду (по шаблону [%\_]); * **EXTERNAL\_ID** - по внешнему коду (по шаблону [%\_]); * **IBLOCK\_ID** - по коду информационного блока; * **DEPTH\_LEVEL** - по уровню вложенности; * **SECTION\_ID** - по разделу-родителю; * *LEFT\_BORDER, RIGHT\_BORDER* - по левой и правой границе (поля **LEFT\_MARGIN** и **RIGHT\_MARGIN**, см. примечание); * **ID** - по коду; * *PROPERTY -* по значениям свойств внутрилежащих элементов, PROPERTY - массив вида Array("код свойства"=>"значение", ...).  Необязательное. По умолчанию записи не фильтруются дополнительно.     Все фильтруемые поля могут содержать перед названием [тип проверки фильтра](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=2683).     Полный список параметров фильтра и дополнительную информацию [b](/api_help/iblock/classes/ciblocksection/getlist.php) в **[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)::[GetList()](/api_help/iblock/classes/ciblocksection/getlist.php)** |

### Смотрите также

* [Поля разделов информационных блоков](/api_help/iblock/fields.php#fsection)

### Примеры использования

```
<?
require($_SERVER["DOCUMENT_ROOT"]."/bitrix/header.php");
$APPLICATION->SetTitle("Каталог");
if(CModule::IncludeModule("iblock"))
{
	// если $ID не задан или это не число, тогда 
	// $ID будет =0, выбираем корневые разделы
	$ID = IntVal($_GET['ID']);
	// выберем папки из информационного блока $BID и раздела $ID
	$items = GetIBlockSectionList($_GET['BID'], $ID, Array("sort"=>"asc"), 10);
	while($arItem = $items->GetNext())
	{
		echo '<a href="catalog.php?BID='.
			urlencode($_GET['BID']).
			'&id='.$arItem['ID'].'">'.$arItem["NAME"].'</a><br>';
		echo $arItem["DESCRIPTION"]."<br>";
	}
}
else
	ShowError("Модуль не установлен");
require($_SERVER["DOCUMENT_ROOT"]."/bitrix/footer.php");
?>Копировать
```

Новинки документации в соцсетях:
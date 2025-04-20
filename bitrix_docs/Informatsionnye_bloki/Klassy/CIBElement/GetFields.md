[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[\_CIBElement](/api_help/iblock/classes/_cibelement/index.php)

GetFields (доступен с 3.1.3)

GetFields
=========

```
array
_CIBElement::GetFields();Копировать
```

Возвращает массив значений полей приведенный в HTML безопасный вид. Также в полях *DETAIL\_PAGE\_URL* и *LIST\_PAGE\_URL* заменяются шаблоны вида #IBLOCK\_ID# и т.п. на их реальные значения, в результате чего в этих полях будут ссылки на страницу детального просмотра и страницу списка элементов. Нестатический метод.

#### Возвращаемое значение

Метод возвращает массив с [полями элемента информационного блока](/api_help/iblock/fields.php#felement) вида Array("поле"=>"преобразованное значение" [, ...]).

#### Смотрите также

* [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)::[GetNext()](/api_help/iblock/classes/ciblockresult/getnext.php)
* [Поля элемента информационного блока](/api_help/iblock/fields.php#felement)
* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetList()](/api_help/iblock/classes/ciblockelement/getlist.php)

#### Примеры использования

```
<?
$res = CIBlockElement::GetByID($_GET["PID"]);
if($obRes = $res->GetNextElement())
{
	$ar_res = $obRes->GetFields();
	echo '<a href="'.$ar_res['detail_page_url'].'">'.$ar_res['name'].'</a>';
}
?>Копировать
```

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)

GetNext (доступен с 3.0.5)

GetNext
=======

Включить вкладки

Описание и параметры

Список шаблонов

Смотрите также

Примеры использования

### Описание и параметры

```
mixed
CIBlockResult::GetNext(
	bool bTextHtmlAuto = true,
	bool use_tilda = true
);Копировать
```

Возвращает массив значений полей приведенный в HTML безопасный вид. Также в полях *DETAIL\_PAGE\_URL* и *LIST\_PAGE\_URL* заменяются шаблоны вида #IBLOCK\_ID# и т.п. на их реальные значения, в результате чего в этих полях будут ссылки на страницу детального просмотра и страницу списка элементов.

Если выборка была из инфоблока свойства которого хранятся отдельно ([Режим хранения свойств в отдельных таблицах](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=2723)), то для правильной обработки значений множественных свойств требуется наличие полей ID и IBLOCK\_ID. Нестатический метод.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| $bTextHtmlAuto | Параметр передается в [CDBResult::GetNext](/api_help/main/reference/cdbresult/getnext.php). Необязательный, по умолчанию принимает *true*. | 6.0.0 |
| use\_tilda |

  

#### Возвращаемое значение

Метод возвращает массив с [полями элемента информационного блока](/api_help/iblock/fields.php#felement) вида Array("поле"=>"преобразованное значение", "~поле"=>"не преобразованное значение", [, ...]) и передвигает курсор на следующую запись.
  
Если достигнута последняя запись (или в результате нет ни одной записи) метод вернет false.

### Список шаблонов

* #SITE\_DIR# - заменяется на константу SITE\_DIR;
* #SERVER\_NAME# - заменяется на константу SITE\_SERVER\_NAME;
* #ID# - заменяется на идентификатор элемента или раздела;
* #CODE# - заменяется на символьный код элемента или раздела;
* #EXTERNAL\_ID# - заменяется на внешний код элемента или раздела;
* #IBLOCK\_TYPE\_ID# - заменяется на идентификатор типа инфоблока которому принадлежит элемент или раздел;
* #IBLOCK\_ID# - заменяется на идентификатор инфоблока которому принадлежит элемент или раздел;
* #IBLOCK\_CODE# - заменяется на символьный код инфоблока которому принадлежит элемент или раздел;
* #IBLOCK\_EXTERNAL\_ID# - заменяется на внешний код инфоблока которому принадлежит элемент или раздел;
* #ELEMENT\_ID# - заменяется на идентификатор элемента;
* #ELEMENT\_CODE# - заменяется на символьный код элемента;
* #SECTION\_CODE# - заменяется на символьный код раздела (использование этого шаблона может привести к дополнительным запросам к базе данных).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)::[GetNextElement()](/api_help/iblock/classes/ciblockresult/getnextelement.php)
* [Поля элемента информационного блока](/api_help/iblock/fields.php#felement)
* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetList()](/api_help/iblock/classes/ciblockelement/getlist.php)

### Примеры использования

```
<?
$res = CIBlockElement::GetByID($_GET["PID"]);
if($ar_res = $res->GetNext())
	echo '<a href="'.$ar_res['DETAIL_PAGE_URL'].'">'.$ar_res['NAME'].'</a>';
else
	echo 'Элемент не найден.';
?>Копировать
```

Новинки документации в соцсетях:
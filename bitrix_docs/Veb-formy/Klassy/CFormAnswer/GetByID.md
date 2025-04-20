[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormAnswer](/api_help/form/classes/cformanswer/index.php)

GetByID (4.0.4)

GetByID
=======

```
CDBResult
CFormAnswer::GetByID(
	int answer_id
)Копировать
```

Возвращает [параметры](/api_help/form/classes/cformanswer/index.php) [ответа](/api_help/form/terms.php#answer) в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *answer\_id* | ID [ответа](/api_help/form/terms.php#answer). |

#### Смотрите также

* [Поля CFormAnswer](/api_help/form/classes/cformanswer/index.php)
* [CFormAnswer::GetList](/api_help/form/classes/cformanswer/getlist.php)

#### Примеры использования

```
<?
$answer_id = 589; // ID ответа
$rsAnswer = CFormAnswer::GetByID($answer_id);
$arAnswer = $rsAnswer->Fetch();
echo "<pre>"; print_r($arAnswer); echo "</pre";
?>Копировать
```

Новинки документации в соцсетях:
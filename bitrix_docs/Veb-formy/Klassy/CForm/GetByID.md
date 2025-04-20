[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetByID (3.1.1)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CForm::GetByID(
	int form_id
	$GET_BY_SID="N"
)Копировать
```

Возвращает [параметры](/api_help/form/classes/cform/index.php) [веб-формы](/api_help/form/terms.php#form) в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *form\_id* | ID веб-формы. |  |
| *GET\_BY\_SID* | Необязательный параметр. | 4.0.0 |

#### Смотрите также

* [Поля CForm](/api_help/form/classes/cform/index.php)
* [CForm::GetBySID](/api_help/form/classes/cform/getbysid.php)
* [CForm::GetList](/api_help/form/classes/cform/getlist.php)

### Примеры использования

```
<?
$FORM_ID = 2;
$rsForm = CForm::GetByID($FORM_ID);
$arForm = $rsForm->Fetch();
echo "<pre>"; print_r($arForm); echo "</pre>";
?>Копировать
```

Новинки документации в соцсетях:
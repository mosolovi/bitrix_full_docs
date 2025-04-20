[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetBySID (3.3.10)

GetBySID
========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CForm::GetBySID(
	string form_sid
)Копировать
```

Возвращает [параметры](/api_help/form/classes/cform/index.php) [веб-формы](/api_help/form/terms.php#form) в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *form\_sid* | Символьный идентификатор веб-формы. |

#### Смотрите также

* [Поля CForm](/api_help/form/classes/cform/index.php)
* [CForm::GetByID](/api_help/form/classes/cform/getbyid.php)
* [CForm::GetList](/api_help/form/classes/cform/getlist.php)

### Примеры использования

```
<?
$FORM_SID = "ANKETA";
$rsForm = CForm::GetBySID($FORM_SID);
$arForm = $rsForm->Fetch();
echo "<pre>"; print_r($arForm); echo "</pre";
?>Копировать
```

Новинки документации в соцсетях:
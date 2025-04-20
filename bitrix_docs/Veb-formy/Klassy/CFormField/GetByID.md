[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormField](/api_help/form/classes/cformfield/index.php)

GetByID (4.0.4)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CFormField::GetByID(
	int field_id
)Копировать
```

Возвращает [параметры](/api_help/form/classes/cformfield/index.php) [вопроса](/api_help/form/terms.php#form)/[поля](/api_help/form/terms.php#form) в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *field\_id* | ID [вопроса](/api_help/form/terms.php#form)/[поля](/api_help/form/terms.php#form). |

#### Смотрите также

* [Поля CFormField](/api_help/form/classes/cformfield/index.php)
* [CFormField::GetBySID](/api_help/form/classes/cformfield/getbysid.php)
* [CFormField::GetList](/api_help/form/classes/cformfield/getlist.php)

### Примеры использования

```
<?
$FIELD_ID = 140; // ID вопроса или поля веб-формы
$rsField = CFormField::GetByID($FIELD_ID);
$arField = $rsField->Fetch();
echo "<pre>"; print_r($arField); echo "</pre";
?>Копировать
```

Новинки документации в соцсетях:
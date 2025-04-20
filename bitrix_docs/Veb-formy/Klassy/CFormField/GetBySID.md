[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormField](/api_help/form/classes/cformfield/index.php)

GetBySID (4.0.4)

GetBySID
========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CFormField::GetBySID(
	int field_sid
)Копировать
```

Возвращает [параметры](/api_help/form/classes/cformfield/index.php) [вопроса](/api_help/form/terms.php#form)/[поля](/api_help/form/terms.php#form) в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *field\_sid* | Символьный идентификатор [вопроса](/api_help/form/terms.php#form)/[поля](/api_help/form/terms.php#form). |  |
| *form\_id* | Необязательный параметр. Значение по умолчанию - "false". | 5.1.1 |

#### Смотрите также

* [Поля CFormField](/api_help/form/classes/cformfield/index.php)
* [CFormField::GetByID](/api_help/form/classes/cformfield/getbyid.php)
* [CFormField::GetList](/api_help/form/classes/cformfield/getlist.php)

### Примеры использования

```
<?
$FIELD_SID = "VS_INTEREST"; // символьный идентификатор вопроса или поля веб-формы
$rsField = CFormField::GetBySID($FIELD_SID);
$arField = $rsField->Fetch();
echo "<pre>"; print_r($arField); echo "</pre";
?>Копировать
```

Новинки документации в соцсетях:
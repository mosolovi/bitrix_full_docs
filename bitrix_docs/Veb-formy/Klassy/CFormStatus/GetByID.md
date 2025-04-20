[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormStatus](/api_help/form/classes/cformstatus/index.php)

GetByID (4.0.4)

GetByID
=======

```
CDBResult
CFormStatus::GetByID(
	int status_id
)Копировать
```

Возвращает [параметры](/api_help/form/classes/cformstatus/index.php) [статуса](/api_help/form/terms.php#status) в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *status\_id* | ID [статуса](/api_help/form/terms.php#status). |

#### Смотрите также

* [Поля CFormStatus](/api_help/form/classes/cformstatus/index.php)
* [CFormStatus::GetList](/api_help/form/classes/cformstatus/getlist.php)

#### Примеры использования

```
<?
$status_id = 1; // ID статуса
$rsStatus = CFormStatus::GetByID($status_id);
$arStatus = $rsStatus->Fetch();
echo "<pre>"; print_r($arStatus); echo "</pre";
?>Копировать
```

Новинки документации в соцсетях:
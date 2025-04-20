[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCertification](/api_help/learning/classes/ccertification/index.php)

GetByID (доступен c 5.1.0)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CCertification::GetByID(
	int ID
);Копировать
```

Возвращает сертификат по идентификатору ID. Учитываются права доступа текущего пользователя. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сертификата. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля сертификата](/api_help/learning/fields.php)
* [CCertification](/api_help/learning/classes/ccertification/index.php)::[GetList](/api_help/learning/classes/ccertification/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$CERTIFICATE_ID = 13;
    
	$res = CCertification::GetByID($CERTIFICATE_ID);
	if ($arCertificate = $res->GetNext())
	{
		echo "Course: ".$arCertificate["COURSE_NAME"].
			" User: ".$arCertificate["USER_NAME"].
			" Score: ".$arCertificate["SUMMARY"];
	}
}
?>Копировать
```

Новинки документации в соцсетях:
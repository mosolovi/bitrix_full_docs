[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

GetCount (4.0.4)

GetCount
========

```
int
CFormResult::GetCount(
	int form_id
)Копировать
```

Возвращает количество [результатов](/api_help/form/terms.php#result) указанной веб-формы. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *form\_id* | ID веб-формы. |

#### Примеры использования

```
<?
$FORM_ID = 4; // ID веб-формы
echo "Количество результатов веб-формы #".$FORM_ID.": ".CFormResult::GetCount($FORM_ID);
?>Копировать
```

Новинки документации в соцсетях:
[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

Mail (4.0.4)

Mail
====

```
bool
CFormResult::Mail(
	int result_id,
	mixed template_id = false
)Копировать
```

Создает почтовое событие для отсылки данных [результата](/api_help/form/terms.php#result) по e-mail. Возвращает "true" в случае успеха, в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *result\_id* | ID [результата](/api_help/form/terms.php#result). |
| *template\_id* | ID почтового шаблона.   Параметр необязательный. По умолчанию - "false" (будут использованы почтовые шаблоны из настроек соответствующей веб-формы). |

#### Примеры использования

```
<?
$RESULT_ID = 189; // ID результата
// создадим почтовое событие для отсылки по EMail данных результата
if (CFormResult::Mail($RESULT_ID))
{
	echo "Почтовое событие успешно создано.";
}
else // ошибка
{
	global $strError;
	echo $strError;
}
?>Копировать
```

Новинки документации в соцсетях:
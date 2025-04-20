[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

GetByID (3.3.10)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CFormResult::GetByID(
	int result_id
)Копировать
```

Возвращает [поля результата](/api_help/form/classes/cformresult/index.php#field), а также некоторые [поля веб-формы](/api_help/form/classes/cform/index.php) и [поля статуса](/api_help/form/classes/cformstatus/index.php) в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

Структура массива в объекте, возвращаемого данным методом:

```
Array
(
	[ID] => ID результата
	[TIMESTAMP_X] => время изменения результата
	[DATE_CREATE] => дата создания результата
	[FORM_ID] => ID веб-формы
	[USER_ID] => ID пользователя создавшего результат (автор)
	[USER_AUTH] => флаг авторизованности автора при создании результата [Y|N]
	[STAT_GUEST_ID] => ID посетителя создавшего результат
	[STAT_SESSION_ID] => ID сессии в которой был создан результат
	[STATUS_ID] => ID статуса в котором находится результат
	[STATUS_TITLE] => заголовок статуса в котором находится результат
	[STATUS_DESCRIPTION] => описание статуса в котором находится результат
	[STATUS_CSS] => имя CSS класса в котором находится результат
	[SID] => символьный идентификатор веб-формы
	[NAME] => заголовок веб-формы
	[IMAGE_ID] => ID изображения веб-формы
	[DESCRIPTION] => описание веб-формы
	[DESCRIPTION_TYPE] => тип описания веб-формы [text|html]
)Копировать
```

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *result\_id* | ID [результата](/api_help/form/terms.php#result). | Удален с версии 4.0.4 |
| *id* | ID [результата](/api_help/form/terms.php#result). | 4.0.4 |

### Смотрите также

* [Поля CFormResult](/api_help/form/classes/cformresult/index.php#field);
* [CFormResult::GetList](/api_help/form/classes/cformresult/getlist.php)
* [CFormResult::GetDataByID](/api_help/form/classes/cformresult/getdatabyid.php);
* [CForm::GetResultAnswerArray](/api_help/form/classes/cform/getresultanswerarray.php)

### Примеры использования

```
<?
$rsResult = CFormResult::GetByID(189);
$arResult = $rsResult->Fetch();
echo "<pre>"; print_r($arResult); echo "</pre>";
?>Копировать
```

Новинки документации в соцсетях:
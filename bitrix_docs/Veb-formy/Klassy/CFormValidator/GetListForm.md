[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormValidator](/api_help/form/classes/cformvalidator/index.php)

GetListForm (6.0.0)

GetListForm
===========

```
CDBResult
CFormValidator::GetListForm(
	int FORM_ID,
	mixed arFilter = array(),
	string &by = "s_sort",
	string &order = "asc",
)Копировать
```

Возвращает список валидаторов, заданных для полей формы, в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *FORM\_ID* | ID [веб-формы](/api_help/form/terms.php#form). |
| *arFilter* | Массив для фильтрации. Необязательный параметр. В массиве допустимы следующие ключи:  * **FIELD\_ID** - ID [вопроса](/api_help/form/terms.php#question); * **ACTIVE** - флаг активности валидатора; * **NAME** - идентификатор валидатора; |
| *by* | Ссылка на переменную с полем для сортировки результирующего списка. Может принимать значения:  * **VALIDATOR\_SID** - ID [валидатора](/api_help/form/terms.php#validator); * **C\_SORT** - индекс сортировки. |
| *оrder* | Ссылка на переменную с порядком сортировки. Может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию. |

Новинки документации в соцсетях:
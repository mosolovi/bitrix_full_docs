[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormValidator](/api_help/form/classes/cformvalidator/index.php)

GetList (6.0.0)

GetList
=======

```
CDBResult
CFormValidator::GetList(
	int FIELD_ID,
	mixed arFilter = array(),
	string &by = "s_sort",
	string &order = "asc",
)Копировать
```

Возвращает список заданных для поля валидаторов в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *FIELD\_ID* | ID [вопроса](/api_help/form/terms.php#question). |
| *arFilter* | Массив для фильтрации. Необязательный параметр. В массиве допустимы следующие ключи:  * **ACTIVE** - флаг активности валидатора; * **NAME** - идентификатор валидатора; |
| *by* | Ссылка на переменную с полем для сортировки результирующего списка. Может принимать значения:  * **VALIDATOR\_SID** - ID [валидатора](/api_help/form/terms.php#validator); * **C\_SORT** - индекс сортировки. |
| *оrder* | Ссылка на переменную с порядком сортировки. Может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию. |

Новинки документации в соцсетях:
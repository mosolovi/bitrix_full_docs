[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CRubric](/api_help/subscribe/classes/crubric/index.php)

GetByID (доступен с 5.0.2)

GetByID
=======

```
CDBResult
CRubric::GetByID(
	int ID
);Копировать
```

Метод выбирает одну рассылку по ее идентификатору. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор рассылки. |  |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult
становятся доступны [поля объекта "Рассылка"](/api_help/subscribe/classes/crubric/crubric.fields.php).

#### Пример использования

```
if($ID>0)
{
	$rubric = CRubric::GetByID($ID);
	if($rubric->ExtractFields("str_"))
		echo $str_NAME;
}Копировать
```

Новинки документации в соцсетях:
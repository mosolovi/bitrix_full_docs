[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

GetRubricList (доступен с 3.1.1)

GetRubricList
=============

```
CDBResult
CPosting::GetRubricList(
	int ID
);Копировать
```

Метод возвращает выборку рассылок, на которые будет отправлен выпуск. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult
становятся доступны [поля объекта "Рассылка"](/api_help/subscribe/classes/crubric/crubric.fields.php): ID, NAME, SORT, LID, ACTIVE.

#### Пример использования

```
//в какие рубрики отправлять
$aPostRub = array();
$post_rub = CPosting::GetRubricList($post_arr["ID"]);
while($post_rub_arr = $post_rub->Fetch())
	$aPostRub[] = $post_rub_arr["ID"];Копировать
```

Новинки документации в соцсетях:
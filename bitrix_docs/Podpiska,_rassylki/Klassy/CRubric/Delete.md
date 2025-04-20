[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CRubric](/api_help/subscribe/classes/crubric/index.php)

Delete (доступен с 5.0.2)

Delete
======

```
mixed
CRubric::Delete(
	int ID
);Копировать
```

Метод удаляет рассылку. Метод нестатический.

**Примечание**. Метод использует внутреннюю транзакцию. Если у вас используется **MySQL** и **InnoDB**, и ранее была открыта транзакция, то ее необходимо закрыть до подключения метода.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор рассылки. |  |

#### Возвращаемые значения

В случае успешного удаления возвращается результат типа [CDBResult](/api_help/main/reference/cdbresult/index.php). В противном случает возвращается false.

#### Пример использования

```
if (($res = CRubric::Delete($ID)) &&
	$res->AffectedRowsCount() < 1 ||
	$res == false)
	echo "Error";Копировать
```

Новинки документации в соцсетях:
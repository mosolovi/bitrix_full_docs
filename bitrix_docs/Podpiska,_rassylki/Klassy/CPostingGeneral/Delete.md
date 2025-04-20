[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

Delete (доступен с 3.1.1)

Delete
======

```
mixed
CPosting::Delete(
	int ID
);Копировать
```

Метод удаляет выпуск по его идентификатору. Метод статический.

**Примечание**. **До версии 17.0.0** метод использовал внутреннюю транзакцию, то есть если использовался **MySQL** и **InnoDB**, и ранее была открыта транзакция, то ее необходимо закрыть до подключения метода.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |

#### Возвращаемые значения

В случае успешного удаления возвращается результат типа [CDBResult](/api_help/main/reference/cdbresult/index.php). В противном случает возвращается false.

#### Пример использования

```
$res = CPosting::Delete($ID);
if(!$res)
	echo "Cannot delete the issue.";
elseif($res->AffectedRowsCount() < 1)
	echo "Already deleted.";
else
	echo "Deleted successfylly.";Копировать
```

Новинки документации в соцсетях:
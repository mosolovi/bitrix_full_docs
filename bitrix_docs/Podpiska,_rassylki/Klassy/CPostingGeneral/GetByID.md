[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

GetByID (доступен с 3.1.1)

GetByID
=======

```
CDBResult
CPosting::GetByID(
	int ID
);Копировать
```

Метод возвращает выпуск по его идентификатору. Метод статический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult
становятся доступны [поля объекта "Выпуск"](/api_help/subscribe/classes/cpostinggeneral/cpostingfields.php).

#### Пример использования

```
$rsPosting = CPosting::GetByID($ID);
$arPosting = $rsPosting->Fetch();
if($arPosting)
	echo htmlspecialchars(print_r($arPosting, true));
else
	echo "Not found";Копировать
```

Новинки документации в соцсетях:
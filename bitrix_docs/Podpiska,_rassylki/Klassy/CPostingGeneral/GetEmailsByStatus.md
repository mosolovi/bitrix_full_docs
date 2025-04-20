[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

GetEmailsByStatus (с версии 8.5.3)

GetEmailsByStatus
=================

```
array
CPosting::GetEmailsByStatus(
	int ID,
	char STATUS
);Копировать
```

Метод возвращает выборку из очереди на отправку. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор выпуска |  |
| STATUS | Статус получателя в очереди. Допустимыми значениями являются:   * "N" письмо отправлено успешно; * "E" - отправлено с ошибкой; * "Y" - ожидает отправки. |  |

#### Возвращаемое значение

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult становятся доступны [поля объекта "Очередь отправки"](/api_help/subscribe/classes/crubric/crubric.fields.php).

#### Смотрите также

* [Поля CPosting](/api_help/subscribe/classes/cpostinggeneral/cpostingfields.php)

Новинки документации в соцсетях:
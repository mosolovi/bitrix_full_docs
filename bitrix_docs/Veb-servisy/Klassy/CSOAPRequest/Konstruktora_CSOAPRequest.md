[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

[CSOAPRequest](/api_help/webservice/classes/csoaprequest/index.php)

Конструктора CSOAPRequest (доступен с 8.0.2)

Конструктора CSOAPRequest
=========================

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
CSOAPRequest::CSOAPRequest(
	string name = "", 
	string namespace = "", 
	array  parameters = array()
);Копировать
```

Конструктор класса.

#### Параметры конструктора

| Параметр | Описание |
| --- | --- |
| *name* | Название сообщения в запросе. |
| *namespace* | Пространство имён сообщения запроса. |
| *parameters* | Параметры запроса в формате *array("Название Параметра" => "Значение")*.  Значение может отдаваться в виде аналогичном тому, что принимает метод [addParameter](addparameter.html) в качестве Value. |

### Пример использования

```
// Вызов DNSLookup метода веб-сервиса
$request = new CSOAPRequest( "DNSLookup", "http://tempuri.org/");Копировать
```

Новинки документации в соцсетях:
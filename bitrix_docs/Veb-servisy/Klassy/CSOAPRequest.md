[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

CSOAPRequest (доступен с 8.0.2)

CSOAPRequest
============

Включить вкладки

Методы класса

Пример использования

### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| [CSOAPRequest](/api_help/webservice/classes/csoaprequest/csoaprequest.php) | Конструктор класса. | 8.0.2 |
| [addSOAPHeader](/api_help/webservice/classes/csoaprequest/addsoapheader.php) | Метод добавляет в SOAP запрос часть заголовка. | 8.0.2 |
| [addBodyAttribute](/api_help/webservice/classes/csoaprequest/addbodyattribute.php) | Метод добавляет атрибут к тегу **body** SOAP запроса. | 8.0.2 |
| [addParameter](/api_help/webservice/classes/csoaprequest/addparameter.php) | Метод добавляет данные для передачи в SOAP запросе. Для веб-сервиса - параметры вызываемого метода. | 8.0.2 |
| *payload* | Метод возвращает сформированный SOAP запрос в виде строки. | 8.0.2 |

### Пример использования

```
// Формируем запрос к веб-сервису ws.strikeiron.com/relauto/iplookup/DNS
$request = new CSOAPRequest("DNSLookup", "http://tempuri.org/");
$request->addSOAPHeader( "LicenseInfo xmlns=\"http://ws.strikeiron.com\"", array(
	"UnregisteredUser" => array(
		"EmailAddress" => "qwerty@mail.ru"
	)
));
$request->addParameter("server", "www.yandex.ru");Копировать
```

Новинки документации в соцсетях:
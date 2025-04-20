[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

Классы модуля Web Service

Классы модуля Web Service
=========================

Включить вкладки

Классы

Реализованные классы

Абстрактные классы

### Классы

Следующие PHP классы используются для реализации веб-сервисов в компонентах.

| Класс | Описание | С версии |
| --- | --- | --- |
| [CWebServiceDesc](/api_help/webservice/classes/cwebservicedesc/index.php) | Структура описывающая методы и типы веб-сервиса. | 7.0.0 |
| [IWebService](/api_help/webservice/classes/iwebservice/index.php) | Интерфейс веб-сервиса для регистрации в CWebService. | 8.0.2 |
| [CWebService](/api_help/webservice/classes/cwebservice/index.php) | Менеджер веб-сервисов. | 8.0.2 |

### Реализованные классы

Следующие PHP классы реализуют SOAP протокол, WSDL, генерацию XML в модуле webservice.

| Класс | Описание | С версии |
| --- | --- | --- |
| [CXMLCreator](/api_help/webservice/classes/cxmlcreator/index.php) | Класс для генерации XML | 8.0.0 |
| [CSOAPFault](/api_help/webservice/classes/csoapfault/index.php) | Класс для обработки ошибок SOAP сервера и клиента. | 8.0.2 |
| [CSOAPRequest](/api_help/webservice/classes/csoaprequest/index.php) | Класс формирует SOAP запрос/конверт. | 8.0.2 |
| [CSOAPServerResponser](/api_help/webservice/classes/csoapserverresponser/index.php) | Интерфейс для реализации пользовательского обработчика SOAP запросов. | 6.5.2 |
| [CSOAPServer](/api_help/webservice/classes/csoapserver/index.php) | Класс SOAP сервер. | 6.5.2 |
| [CSOAPClient](/api_help/webservice/classes/csoapclient/index.php) | Класс SOAP клиент. | 8.0.0 |
| CWSDLCreator | Класс для автоматической генерации WSDL для веб-сервиса. Document/literal binding only. | 7.0.0 |
| CSOAPCodec | Класс трансформирует данные в XML согласно описанию веб-сервиса. | 7.0.0 |
| CSOAPResponse | Класс формирует/обрабатывает SOAP ответы. | 6.5.2 |
| CWSSOAPResponser | Класс реализующий обработку запросов к веб-сервисам через SOAP. Наследует CSOAPServerResponser. | 6.5.2 |

### Абстрактные классы

| Класс | Описание | С версии |
| --- | --- | --- |
| CSOAPHeader | Абстрактный класс для обработки SOAP пакета. | 8.0.2 |
| CSOAPBody | Абстрактный класс для обработки SOAP пакета. | 8.0.2 |
| CSOAPEnvelope | Абстрактный класс для обработки SOAP пакета. | 6.5.2 |

Новинки документации в соцсетях:
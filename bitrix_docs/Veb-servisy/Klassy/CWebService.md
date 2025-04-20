[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

CWebService (доступен с 8.0.2)

CWebService
===========

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| **SetComponentContext** | Метод запоминает контекст конфигурации компонента (**$arParams**) для передачи его в контекст вызова метода веб-сервиса. | 8.0.2 |
| **GetComponentContext** | Метод возвращает контекст конфигурации компонента (**$arParams**), который предоставляет веб-сервис. Может вызываться из методов веб-сервиса: **CWebService::GetComponentContext**. | 8.0.2 |
| **SOAPServerProcessRequest** | Метод вызывает обработчик SOAP сервера для обработки входящего запроса по методу POST. Обработчик вызывается для экземпляра веб-сервиса указанного в параметрах метода. | 8.0.2 |
| [RegisterWebService](/api_help/webservice/classes/cwebservice/registerwebservice.php) | Метод регистрирует веб-сервис. | 8.0.2 |
| **GetSOAPServerRequest** | Метод возвращает SOAP запрос (string), который принял SOAP Сервер. | 8.0.2 |
| **GetSOAPServerResponse** | Метод возвращает ответ (string) SOAP Сервера. | 8.0.2 |
| **MethodRequireHTTPAuth** | Метод проверяет, пройдена ли HTTP Basic авторизация. Используется для методов веб-сервисов, которые требует авторизацию. | 8.0.2 |
| **TestComponent** | Метод вызывает [IWebService::TestComponent](/api_help/webservice/classes/iwebservice/testcomponent.php) запрашиваемого зарегистрированного веб-сервиса. | 8.0.2 |
| **GetWSDL** | Метод возвращает автоматически сгенирированный WSDL код  (если **CWebServiceDesc->wsdlauto** равно **true**). | 8.0.2 |
| **GetDefaultEndpoint** | Метод возвращает точку доступа (например, *http://site.ru/ws.php*) для веб-сервиса по умолчанию. | 8.0.2 |
| **GetDefaultTargetNS** | Метод возвращает пространство имён для веб-сервиса по умолчанию. | 8.0.2 |
| **GetWebServiceDeclaration** | Метод возвращает экземпляр класса **CWebServiceDesc** через интерфейс [IWebService](/api_help/webservice/classes/iwebservice/index.php) веб-сервиса. | 8.0.2 |
| **GetInterface** | Метод возвращает экземпляр класса веб-сервиса, реализующий IWebService. | 8.0.2 |

Новинки документации в соцсетях:
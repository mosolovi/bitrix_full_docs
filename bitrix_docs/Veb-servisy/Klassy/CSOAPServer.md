[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

CSOAPServer (доступен с 6.5.2)

CSOAPServer
===========

Включить вкладки

Методы класса

Пример использования

### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| **GetRequestData** | Метод возвращает принятый запрос SOAP пакета. | 6.5.2 |
| **GetResponseData** | Метод возвращает ушедший в ответ SOAP пакет. GetResponseData можно вызвать только после ProcessRequest. | 6.5.2 |
| **boolean  AddServerResponser(  CSOAPServerResponser &respobject )** | Метод регистрирует обработчик SOAP запроса. Обработчики, наследующие, интерфейс **CSOAPServerResponser**, должны быть зарегистрированы заранее, до вызова метода **ProcessRequest**. | 6.5.2 |
| **ShowRawResponse** | Метод формирует и отсылает SOAP Response пакет вместе с данными в виде **CXMLCreator**. | 6.5.2 |
| **ShowResponse** | Метод формирует и отсылает SOAP Response пакет, после преобразования данных. | 6.5.2 |
| **ShowSOAPFault** | Метод формирует и отсылает SOAP Response пакет с ошибкой. | 6.5.2 |
| **ProcessRequest** | Метод запускает обработку SOAP запроса. К этому моменту обработчики [CSOAPServerResponser](/api_help/webservice/classes/csoapserverresponser/index.php) должны быть зарегистрированы методом **AddServerResponser**. Возвращает *true* если обработка успешна, иначе *false*. | 6.5.2 |
| **stripHTTPHeader** | Метод отрезает HTTP заголовок в том месте, где начинается XML-документ. | 6.5.2 |

### Пример использования

В этом примере в **$arParams["SOAPSERVER\_RESPONSER"]** содержаться объекты
обработчики SOAP.

Обычно SOAP-обработчик создаётся в компоненте, сохраняется в массив в
**$arParams["SOAPSERVER\_RESPONSER"]** и далее, когда включается компонент
webservice.server, выполняется следующий код.

```
// В компоненте обработчика
// Создаем экземпляр обработчика
$research =& new CMSSOAPResearch();
// Конфигурируем обработчик
$research->provider_id = '{XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}';
$research->service_id = '{XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}';
$research->add_tittle = "";
$research->query_path = "http://{$_SERVER[HTTP_HOST]}/ws/wscauth.php";
$research->registration_path = "http://{$_SERVER[HTTP_HOST]}/ws/wscauth.php";
// Сохраняем для передачи в webservice.server
$arParams["SOAPSERVER_RESPONSER"] = array( &$research );
.........
// В компоненте webservice.server
$server = new CSOAPServer();
for ($i = 0; $i<count($arParams["SOAPSERVER_RESPONSER"]); $i++)
{
	$server->AddServerResponser($arParams["SOAPSERVER_RESPONSER"][$i]);
}
$result = $server->ProcessRequest();Копировать
```

Новинки документации в соцсетях:
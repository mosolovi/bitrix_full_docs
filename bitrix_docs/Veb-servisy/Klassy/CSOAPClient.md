[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

CSOAPClient (доступен с 8.0.0)

CSOAPClient
===========

Включить вкладки

Методы класса

Примеры

### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| **CSOAPClient** | Конструктор класса. Настраивает SOAP клиент на конкретный сервер ($server), точку доступа soap сервера ($path='/'), порт web сервера ($port). | 8.0.0 |
| **send** | Метод отсылает SOAP запрос сформированный CSOAPRequest. | 8.0.0 |
| **setTimeout** | Метод устанавливает время ожидания ответа SOAP сервера. | 8.0.0 |
| **getRawRequest** | Метод возвращает строку - запрос ушедший SOAP серверу. | 8.0.0 |
| **getRawResponse** | Метод возвращает строку - ответ SOAP сервера. | 8.0.0 |
| **setLogin** | Метод устанавливает логин для авторизации через HTTP Basic для SOAP запроса. | 8.0.0 |
| **setPassword** | Метод устанавливает пароль для авторизации через HTTP Basic для SOAP запроса. | 8.0.0 |
| **login** | Метод возвращает установленный логин. | 8.0.0 |
| **password** | Метод возвращает установленный пароль. | 8.0.0 |

### Примеры

#### Пример использования номер 1 (внутренний тест)

  

```

function TestComponent() 
{
	global $APPLICATION;
	$client = new CSOAPClient( "bitrix.soap", $APPLICATION->GetCurPage() );
	$request = new CSOAPRequest( "wsTestStartOut1", "http://bitrix.soap/" );
	$request->addParameter("str1", "qwe");
	$request->addParameter("str2", "fjdfhgfdh");
	$request->addParameter("int3", "123");
	$response = $client->send( $request );
	echo "Call wsTestStartOut1";
	if ( $response->isFault() )
	{
		print( "SOAP fault: " . $response->faultCode(). " - " . $response->faultString() . "" );
	}
	else
		echo "[OK]: ".mydump($response->Value);		
}Копировать
```

#### Пример использования номер 2 (внешний тест)

```

function TestComponent() 
{
	$client = new CSOAPClient("ws.strikeiron.com", "/relauto/iplookup/DNS");
	$request = new CSOAPRequest( "DNSLookup", "http://tempuri.org/");
	$request->addSOAPHeader( "LicenseInfo xmlns=\"http://ws.strikeiron.com\"",
			array("UnregisteredUser" => array( "EmailAddress" => "qwerty@mail.ru" ))
		);
	$request->addParameter("server", "www.yandex.ru");
	$response = $client->send( $request );
		
	echo "SOAPRequest: ".htmlspecialchars($client->getRawRequest());
	echo "SOAPResponse: ".htmlspecialchars($client->getRawResponse());
}Копировать
```

#### Пример использования номер 3

```
CModule::IncludeModule('webservice');
$client = new CSOAPClient("192.168.1.1", '/path_to_webservice/');
$request = new CSOAPRequest("myMethod", "http://some-namespace/");
$client->setLogin('my_login');
$client->setPassword('my_password');
$request->addParameter("myMethodParam", "xxxxx");
$response = $client->send($request);
 
if ( $response->isFault() ) 
{ 
	print( "SOAP fault: " . $response->faultCode(). " - " . $response->faultString() . "" ); 
} 
else 
{ 
	echo "[OK]: ".print_r($response->Value, 1);    
}Копировать
```

Новинки документации в соцсетях:
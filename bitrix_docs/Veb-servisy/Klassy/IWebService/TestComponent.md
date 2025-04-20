[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

[IWebService](/api_help/webservice/classes/iwebservice/index.php)

TestComponent (доступен с 8.0.2)

TestComponent
=============

```
void
IWebService::TestComponent();Копировать
```

Метод запускает внутреннее тестирование веб-сервиса с использованием SOAP
клиента. Этот метод вызывается из публичной части веб-сервиса. Нестатический метод.

```

class CCheckAuthWS extends IWebService
{
	...
    
	function TestComponent() 
	{
		global $APPLICATION;
		$client = new CSOAPClient("bitrix.soap", $APPLICATION->GetCurPage());
		// HTTP Authorization required by GetHTTPUserInfo method
		$client->setLogin("admin");
		$client->setPassword("123456");
		$request = new CSOAPRequest("GetHTTPUserInfo", CWebService::GetDefaultTargetNS());
		//$request->addParameter("stub", 0);
		$response = $client->send( $request );
		if ($response->FaultString)
			echo $response->FaultString;
		else
			echo "Call GetHTTPUserInfo(): 
".mydump($response->Value)."
";
	}
	...
}Копировать
```

Новинки документации в соцсетях:
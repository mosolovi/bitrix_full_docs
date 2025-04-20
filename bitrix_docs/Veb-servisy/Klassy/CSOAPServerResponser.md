[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

CSOAPServerResponser (доступен с 6.5.2)

CSOAPServerResponser
====================

Включить вкладки

Методы интерфейса

Параметры метода

Пример использования

### Методы интерфейса

| Метод | Описание | С версии |
| --- | --- | --- |
| void  OnBeforeRequest(  CSOAPServer &cserver ) | Метод вызывается для всех обработчиков **CSOAPServerResponser** зарегистрированных в обрабатывающем SOAP сервере при наступлении события, когда получен запрос к серверу, но ещё не началось его раскодирование. | 6.5.2 |
| void  OnAfterResponse(  CSOAPServer &cserver ) | Метод вызывается для всех обработчиков **CSOAPServerResponser** зарегистрированных в обрабатывающем SOAP сервере при наступлении события, когда завершилась обработка запроса и ответ уже отослан (**ProcessRequestBody** вернула *true*). | 6.5.2 |
| boolean  ProcessRequestBody(  CSOAPServer &cserver,   CDataXMLNode body ) | Метод обработчик запроса SOAP сервера. Если метод обработал запрос и ответил вызовом **ShowResponse**, то возвращается *true*. Иначе возвращается *false* и вызовы **ProcessRequestBody** обработчиков продолжаются по цепочке пока не будет найден обработчик запроса, либо пока список обработчиков не иссякнет. | 6.5.2 |

### Параметры метода

| Параметр | Описание |
| --- | --- |
| cserver | Ссылка на объект **CSOAPServer**, обрабатывающего soap запрос. |
| body | Часть XML запроса от элемента, следующего за тегом body в виде **CDataXMLNode**. |

### Пример использования

```

class CMSSOAPResearch extends CSOAPServerResponser
{
	var $provider_id;    
	var $service_id;
	var $add_tittle;
	var $query_path;
	var $registration_path;
	function OnBeforeRequest(&$cserver) 
	{
		AddMessage2Log(mydump($cserver->GetRequestData()));    
	}
	function ProcessRequestBody(&$cserver, $body) 
	{
		$functionName = $body->name();
		$namespaceURI = $body->namespaceURI();
		$requestNode = $body;
        
		if ($functionName == "Registration")
		{
			$root = new CXMLCreator("RegistrationResponse");
			$root->setAttribute("xmlns", "urn:Microsoft.Search");
            
			$regres = new CXMLCreator("RegistrationResult");
			$root->addChild($regres);
                        
			$prup = new CXMLCreator("ProviderUpdate");
			$prup->setAttribute("xmlns", "urn:Microsoft.Search.Registration.Response");
			$prup->setAttribute("revision", "1");             
			$prup->setAttribute("build", "1");
			$regres->addChild($prup);    
            
			$stat = new CXMLCreator("Status");
			$stat->setData("SUCCESS");
			$prup->addChild($stat);
                        
			$providers = array(
                
				"Provider" => array (
					"Message" => "Тестовая служба.",
					"Id" => "{$this->provider_id}",
					"Name" => "Тестовая служба. {$this->add_tittle}",
					"QueryPath" => $this->query_path,
					"RegistrationPath" => $this->registration_path,
					"AboutPath" => "http://www.bitrix.ru/",
					"Type" => "SOAP",
					"Revision" => "1",
					"Services" => array(
						"Service" => array(
							"Id" => "{$this->service_id}",
							"Name" => "Тестовая служба. {$this->add_tittle}",
							"Description" => "Тестовая служба для тестирования soap сервера.",
							"Copyright" => "(c) Bitrix.",
							"Display" => "On",
							"Category" => "ECOMMERCE_GENERAL",
							"Parental" => "Unsupported",
						)
					)                        
				)                        
            
			);
			$providersEncoded = CXMLCreator::encodeValueLight("Providers", $providers);
			$prup->addChild($providersEncoded);        
            
			$cserver->ShowRawResponse($root, true);
            
			AddMessage2Log($cserver->GetResponseData());
            
			return true;
		}
        
		return false;
	}
}Копировать
```

Новинки документации в соцсетях:
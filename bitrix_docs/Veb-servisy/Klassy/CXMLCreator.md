[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

CXMLCreator (доступен с 8.0.0)

CXMLCreator
===========

Включить вкладки

Описание и список методов

Пример

### Описание и список методов

Класс представляет собой тег XML-документа, состоящий из атрибутов, дочерних
элементов, текстового содержимого и CDATA контента.

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| **CXMLCreator(  string tag,   boolean cdata )** | Конструктор класса. Принимает в качестве параметра название тега. | 8.0.0 |
| **static  CXMLCreator  [createTagAttributed](/api_help/webservice/classes/cxmlcreator/createtagattributed.php)(  string heavyTag )** | Метод создаёт тег **CXMLCreator** из названия тега *heavyTag*, записанного в особенном формате. | 8.0.0 |
| **static  CXMLCreator  encodeValueLight(  string name,   AnyType Value )** | Метод создаёт дерево XML документа с именем *Name* и строением *Value*. *Name* - название тега в формате *heavyTag*метода **createTagAttributed**. *Value* может быть любым типом данных, например, последовательностью вложенных ассоциативных массивов. Смотрите пример использования ниже. | 8.0.0 |
| **setCDATA** | Метод устанавливает CDATA-контент тега. | 8.0.0 |
| **setAttribute** | Метод устанавливает атрибут тега. | 8.0.0 |
| **setData** | Метод устанавливает текстовое содержимое тега. | 8.0.0 |
| **setName** | Метод устанавливает название тега. | 8.0.0 |
| **addChild** | Метод добавляет элемент XML документа в список своих детей. | 8.0.0 |
| **getChildrenCount** | Метод возвращает количество подчинённых элементов XML документа. | 8.0.0 |
| **getXML** | Метод возвращает XML документ в виде строки. | 8.0.0 |
| **getXMLHeader** | Метод возвращает заголовок XML документа. | 8.0.0 |

### Пример

Пример применения в обработчике SOAP запросов SOAP сервера

  

```

class CMSSOAPResearch extends CSOAPServerResponser
{
	...
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
			$providersEncoded = CSOAPRequest::encodeValueLight("Providers", $providers);
			$prup->addChild($providersEncoded);        
            
			...
            
			return true;
		}
        
	return false;
	}
}Копировать
```

Новинки документации в соцсетях:
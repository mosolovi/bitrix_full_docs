[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

CWebServiceDesc (доступен с 7.0.0)

CWebServiceDesc
===============

Включить вкладки

Веб-сервис

Типы данных

Описание веб-сервиса

Пример использования

### Веб-сервис

IWebService

| Параметр | Тип | Описание |
| --- | --- | --- |
| *wsdlauto* | boolean | Параметр указывает, нужно ли генерировать WSDL-код автоматически. |
| *wstargetns* | string | Пространство имён, например, *http://bitrix.ru/* |
| *wsendpoint* | string | Конечная точка (точка доступа) веб-сервиса - например, *<http://bitrix.ru/ws/testws.php>* |
| *classes* | array | Описатель методов веб-сервиса. |
| *structTypes* | array | Описатель сложных типов данных веб-сервиса (структуры). |
| *classTypes* | array | Описатель сложных типов данных, десериализуемых из XML в экземпляры классов. |

Класс **CWebServiceDesc** (описатель веб-сервиса) должен быть
полностью инициализирован. Этот класс возвращается методом [IWebService::GetWebServiceDesc](/api_help/webservice/classes/iwebservice/getwebservicedesc.php).
После регистрации описателя веб-сервиса, в его экземпляре автоматически
создаётся экземпляр SOAP сервера и экземпляр WSDL генератора.

Методы веб-сервисов всегда:

* принадлежат классу, реализующему веб-сервис;
* полностью описывают свои исходящие и входящие параметры;
* строго соблюдают типы входящих\исходящих данных согласно их описанию.

### Типы данных

Типы данных используемые методами веб-сервиса могут быть двух типов:

* **Простые типы** - string, bool, boolean, int, integer, double, float,
  number;
* **Сложные типы** - массивы, структуры (сериализуются в ассоциативные
  массивы), классы (сериализуются в экземпляры классов); Описываются с помощью
  *structTypes*, *classTypes*.

Типы данных описываются в трёх местах в описателе веб-сервиса
**CWebServiceDesc**:

* **classes** - массивы как параметры методов (см. [описание классов](/api_help/webservice/classes/index.php));
* **structTypes** - структуры;
* **classTypes** - классы;

### Описание веб-сервиса

Если автоматически генерируется WSDL, то генерируется **Document/Literal**
binding. SOAP сервер поддерживает также исключительное Document/Literal binding.
Для всех типов и параметров генерируется XSD схема.

| Параметр | Описание |
| --- | --- |
| *classes* | Этот член класса обязательно должен быть инициализирован. Описывает методы веб-сервиса через его класс, входящие и исходящие параметры. Может оперировать массивами (как сложными типами данных) если указывается атрибут **arrType** и **varType**. При этом для массива автоматически создаётся свой тип данных в XSD схеме.  Ассоциативный массив:   ``` $wsdesc->classes = array( 	"Имя класса содержащего метод веб-сервиса" => array( 		"Название метода веб-сервиса" => array( 			// означает что метод публичный 			"type"        => "public",                         			"name"        => "Название метода веб-сервиса", 			// описание принимаемых методом параметров 			// "strict" => "no" - значит, что параметр не обязательный.              //                    Его можно не передавать в soap запросе. 			"input"        => array( 				// "ТипДанных" - название сложного или простого типа данных 				"ИмяПараметра" =>array("varType" => "ТипДанных"[, "strict" => "no"]), 				// Так описываются параметры - массивы 				// varType - название массива (как типа данных, для xsd схемы) 				// arrType - тип элементов массива 				"ИмяПараметра" =>array( 					"varType" => "ArrayOf"."ТипДанных", 					"arrType" => "ТипДанных" 				), 				// Пример передачи сложных типов данных. 				// Сложные типы должны быть описаны в structTypes, classTypes 				"ИмяПараметра" =>array("varType" => "sGenTest"), 				// Пример передачи массива сложного типа (структуры) 				"ИмяПараметра" =>array( 					"varType" => "ArrayOfSGenTest", 					"arrType" => "sGenTest" 				) 			... 			// описание исходящих параметров 			"output"    => array( 				// Здесь может быть описан только один исходящий параметр 				"user" => array("varType" => "ТипДанных") 			), 			// требуется ли для вызова метода пройти HTTP Basic авторизацию. 			"httpauth" => "Y или N" 		), ... 	), ... );Копировать ``` |
| *structTypes* | Описывает структурные типы данных. В PHP они представлены ассоциативными массивами. В **VisualStudio** они представлены структурами (или классами).   SOAP сервер десериализует эти типы в ассоциативные массивы. Имена этих типов данных могут быть использованы в описателе параметров методов веб-сервиса в *classes*. Для этих типов данных автоматически создаётся **ComplexType** в xsd схеме.  Ассоциативный массив:  ``` $wsdesc->structTypes["ИмяСтруктуры"] = 	array( 		"ИмяПоля" => array("varType" => "ТипДанных"), 		... 	);Копировать ``` |
| *classTypes* | Описывает классы как типы данных. В PHP, **VisualStudio** они представленны классами.   SOAP сервер десериализует эти типы в экземпляры описанных классов. На момент десериализации класс должен быть определён (например, в компоненте, реализующем веб-сервис). Имена этих типов данных могут быть использованы в описателе параметров методов веб-сервиса в classes. Для этих типов данных автоматически создается **ComplexType** в xsd схеме.  Ассоциативный массив:  ``` $wsdesc->classTypes["ИмяКласса"] = 	array( 		"ИмяПоля" => array("varType" => "ТипДанных"), 		... 	);Копировать ``` |

### Пример использования

В качестве хорошего примера использования **CWebServiceDesc**, вы можете
исследовать вот этот файл:
*\bitrix\modules\webservice\classes\general\webservice.wsdl.php*:

```

class CCheckAuthWS extends IWebService
{
	...
	function GetWebServiceDesc() 
	{
		$wsdesc = new CWebServiceDesc();
		$wsdesc->wsname = "bitrix.webservice.checkauth";
		$wsdesc->wsclassname = "CCheckAuthWS";
		$wsdesc->wsdlauto = true;
		$wsdesc->wsendpoint = CWebService::GetDefaultEndpoint();
		$wsdesc->wstargetns = CWebService::GetDefaultTargetNS();
        
		$wsdesc->classTypes = array();
		$wsdesc->structTypes["CUser"] =
		array(
			"ID" => array("varType" => "integer"),
			"NAME" => array("varType" => "string"),
			"TIMESTAMP_X" => array("varType" => "string"),
			"LOGIN" => array("varType" => "string"),
			"PASSWORD" => array("varType" => "string"),
			"CHECKWORD" => array("varType" => "string"),
			"ACTIVE" => array("varType" => "string"),
			"LAST_NAME" => array("varType" => "string"),
			"EMAIL" => array("varType" => "string")        
		);
        
		$wsdesc->classes = array(
			"CCheckAuthWS" => array(
				"CheckAuthorization" => array(
					"type"        => "public",
					"name"        => "CheckAuthorization",
					"input"        => array(
						"user" =>array("varType" => "string"),
						"password" =>array("varType" => "string")
					),
					"output"    => array(
						"user" => array("varType" => "CUser")
					)
				),
				"GetHTTPUserInfo" => array(
					"type"        => "public",
					"name"        => "GetHTTPUserInfo",
					"input"        => array(),
					"output"    => array(
						"user" => array("varType" => "CUser")
					),
					"httpauth" => "Y"
				)
			)
		);
        
		return $wsdesc;
	}
    
	...
}Копировать
```

Новинки документации в соцсетях:
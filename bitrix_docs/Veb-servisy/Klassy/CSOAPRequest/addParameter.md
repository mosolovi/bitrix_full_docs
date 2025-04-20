[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

[CSOAPRequest](/api_help/webservice/classes/csoaprequest/index.php)

addParameter (доступен с 8.0.2)

addParameter
============

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
void
CSOAPRequest::addParameter( 
	string name, 
	ЛюбойТипДанных value
)Копировать
```

Метод добавляет данные для передачи в SOAP запрос. Для веб-сервиса -
параметры вызываемого метода. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *name* | Название параметра. |
| *value* | Обычно - ассоциативный массив описывающий содержание сообщения в заголовке запроса. См. [CXMLCreator::encodeValueLight](/api_help/webservice/classes/cxmlcreator/index.php). |

### Пример использования

```
// Пример создания запроса для вызова веб-сервиса из файла webservice.wsdl.phpt
$request = new CSOAPRequest( "wsTestStart4", "http://bitrix.soap/" );
$request->addParameter("str1", "qwe");
$request->addParameter("str2", array(
	"1:ArrayOfsGenTestXEl" => array(
		"id" => "123",
		"name" => "qwe",
		"testa" => array(
			"1:ArrayOfsGenLiteEl" => array("id" => "56", "name" => "asd"),
			"2:ArrayOfsGenLiteEl" => array("id" => "13", "name" => "fjhg")
		)
	),
	"2:ArrayOfsGenTestXEl" => array(
		"id" => "7653",
		"name" => "dfgsdf DASD",
		"testa" => array(
			"1:ArrayOfsGenLiteEl" => array("id" => "78", "name" => "ty"),
			"2:ArrayOfsGenLiteEl" => array("id" => "99", "name" => "3425rte")
		)
	)
));Копировать
```

Новинки документации в соцсетях:
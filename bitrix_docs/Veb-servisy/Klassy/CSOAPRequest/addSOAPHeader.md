[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

[CSOAPRequest](/api_help/webservice/classes/csoaprequest/index.php)

addSOAPHeader (доступен с 8.0.2)

addSOAPHeader
=============

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
void
CSOAPRequest::addSOAPHeader( 
	string name, 
	ЛюбойТипДанных value 
)Копировать
```

Метод добавляет в SOAP запрос часть заголовка. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| name | Название сообщения в заголовке soap запроса. |
| value | Обычно - ассоциативный массив описывающий содержание сообщения в заголовке запроса. См. CXMLCreator::encodeValueLight. |

### Пример использования

```
$request->addSOAPHeader( 
	"LicenseInfo xmlns=\"http://ws.strikeiron.com\"",
	array(
		"UnregisteredUser" => array( "EmailAddress" => "qwerty@mail.ru" )
	)
);Копировать
```

Новинки документации в соцсетях:
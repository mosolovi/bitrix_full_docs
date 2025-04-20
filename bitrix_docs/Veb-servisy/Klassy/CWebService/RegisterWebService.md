[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

[CWebService](/api_help/webservice/classes/cwebservice/index.php)

RegisterWebService (доступен с 8.0.2)

RegisterWebService
==================

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
boolean
CWebService::RegisterWebService(string className);Копировать
```

Метод регистрирует веб-сервис. Если операция проведена успешно, возвращается
*true*, иначе *false*. Нестатический метод.

Если веб-сервис реализован через систему компонентов, то
**RegisterWebService** вызывается автоматически в компоненте
**webservice.server**. В этом случае *className =
$arParams["WEBSERVICE\_NAME"]*.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| className | Название класса веб-сервиса. реализующего интерфейс **IWebService**. |

### Пример использования

```

// В компоненте webservice.server
CWebService::RegisterWebService($arParams["WEBSERVICE_CLASS"]);
// В компоненте веб-сервиса
$arParams["WEBSERVICE_NAME"] = "bitrix.webservice.checkauth";
// Следующий параметр прямо передается в SOAPServerProcessRequest
$arParams["WEBSERVICE_CLASS"] = "CCheckAuthWS";
$arParams["WEBSERVICE_MODULE"] = "";
$APPLICATION->IncludeComponent(
	"bitrix:webservice.server",
	"",
	$arParams
);Копировать
```

Новинки документации в соцсетях:
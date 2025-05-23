[Веб-сервисы](/api_help/webservice/index.php)

Для разработчиков

Для разработчиков
=================

С помощью модуля можно создавать свои веб-сервисы и клиенты сторонних веб-сервисов.

Перед использованием модуля необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<?    
if(CModule::IncludeModule("webservice"))
{  
	//здесь можно использовать функции и классы модуля
} 
?>Копировать
```

Модуль включает в себя следующие Компоненты 2.0:

  

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| Check Authentication | **webservice.checkauth** | Возвращает данные по пользователю, если он правильно авторизован. Компонент может рассматриваться как пример реализации веб-сервиса, содержащего методы проверки авторизации пользователя и получения информации по авторизованному пользователю (компонент не описывается). |
| [SOAP&WSDL сервер](https://dev.1c-bitrix.ru/user_help/components/services/web_service/webservice_server.php) | **webservice.server** | Реализует конечную точку (EndPoint) для сконфигурированного веб-сервиса на основе SOAP/WSDL. |
| [Веб-сервисы модуля статистики](https://dev.1c-bitrix.ru/user_help/components/services/web_service/webservice_statistic.php) | **webservice.statistic** | Веб-сервис, отдающий статистические данные по сайту, например, для гаджета статистики для боковой панели OC Windows Vista. |

Новинки документации в соцсетях:
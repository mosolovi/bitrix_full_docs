[Пространство имён Bitrix](/api_d7/bitrix/index.php)

[DAV](/api_d7/bitrix/dav/index.php)

Dav

Dav
===

**Dav** - пространство имён для классов, работающих по протоколу WebDAV.

  
  

С версии 23.100.0 модуль webdav не перехватывает PATH, PUT, OPTIONS и подобные запросы, если маршруты были сконфигурированы через новый [роутинг](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&CHAPTER_ID=013764).

| Класс, пространство имен | Описание |
| --- | --- |
| [Application](/api_d7/bitrix/dav/application/index.php) | Класс обеспечивает доступ клиента не по обычному паролю, а по паролю приложения (caldav, carddav, webdav). Является расширением класса [\Bitrix\Main\Authentication\Application](/api_d7/bitrix/main/authentication/application/index.php). |
| [Profile](/api_d7/bitrix/dav/profile/index.php) | Пространство имён для классов, обслуживающих генерацию специальных профилей для синхронизации по протоколу DAV. |
| [TokensTable](/api_d7/bitrix/dav/tokenstable/index.php) | Класс для работы с таблицами токенов. |

Новинки документации в соцсетях:
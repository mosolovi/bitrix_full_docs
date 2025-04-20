[Пространство имён Bitrix](/api_d7/bitrix/index.php)

Главный модуль (с версии 12.0.2)

Главный модуль
==============

**Main** - пространство имён для классов и методов **Главного модуля** системы. Модуль не нуждается в специальном коде для подключения.

| Класс, простраство имён | Описание |
| --- | --- |
| [Application](/api_d7/bitrix/main/application/index.php) | Базовый класс для любых приложений. |
| [Authentication](/api_d7/bitrix/main/authentication/index.php) | Пространство имён для классов аутентификации пользователей. |
| [Context](/api_d7/bitrix/main/context/index.php) | Класс для работы с контекстом |
| [Config](/api_d7/bitrix/main/config/index.php) | Пространство имён для классов настроек. |
| [Data](/api_d7/bitrix/main/data/index.php) | Пространство имён классов для работы с кешем, в том числе с управляемым. |
| [DB](/api_d7/bitrix/main/db/index.php) | Пространства имён для классов, работающих с Базой данных |
| [Diag](/api_d7/bitrix/main/diag/index.php) | Пространства имён для классов диагностики. |
| [Entity](/api_d7/bitrix/main/entity/index.php) | Пространство имён для работы с сущностями. |
| [Environment](/api_d7/bitrix/main/environment/index.php) | Класс работы с окружением. |
| [EventManager](/api_d7/bitrix/main/EventManager/index.php) | Класс кратко- и долгосрочной регистрации обработчиков событий. |
| [FinderDestTable](/api_d7/bitrix/main/finderdesttable/index.php) | класс для работы с таблицей сущностей, выбираемые в диалоге выбора, в списке **Последние**. |
| [Grid](/api_d7/bitrix/main/grid/index.php) | Пространство имён для работы с гридом (табличным элементом управления). |
| [GroupTaskTable](/api_d7/bitrix/main/grouptasktable/index.php) | класс описывает ORM-сущность GroupTaskTable. |
| [HttpApplication](/api_d7/bitrix/main/httpapplication/index.php) | класс отвечает за обычный http-хит на сайте. |
| [HttpRequest](/api_d7/bitrix/main/httprequest/index.php) | Класс управляет объектом HTTP запросов, содержащим информацию о текущем запросе. |
| [IO](/api_d7/bitrix/main/io/index.php) | Объектно-ориентированная работа с файлами. |
| [Loader](/api_d7/bitrix/main/loader/index.php) | класс для загрузки необходимых файлов, классов и модулей. |
| [Localization](/api_d7/bitrix/main/localization/index.php) | Пространство имён для работы с языковыми файлами. |
| [Mail](/api_d7/bitrix/main/mail/index.php) | Описание пространства имён. |
| [Page](/api_d7/bitrix/main/page/index.php) | Пространство имён для классов, работающих со страницей продукта. |
| [Replica](/api_d7/bitrix/main/replica/index.php) | Пространство имён для классов репликации главного модуля. |
| [Request](/api_d7/bitrix/main/request/index.php) | Класс для работы с объектом запроса. |
| [Result](/api_d7/bitrix/main/result/index.php) | Класс результата выполнения запроса. |
| [Security](/api_d7/bitrix/main/security/index.php) | Пространство имён для классов, отвечающих за безопасность. |
| [Server](/api_d7/bitrix/main/server/index.php) | Класс объектов сервера. |
| [Service](/api_d7/bitrix/main/service/index.php) | Пространство имён для классов интеграций с различными сервисами. |
| [Text](/api_d7/bitrix/main/text/index.php) | пространство имён для работы с текстом: классы для конвертации текста и другие. |
| [Type](/api_d7/bitrix/main/type/index.php) | Пространство имён для работы с типами данных: дата, файл и другие. |
| [UI](/api_d7/bitrix/main/ui/index.php) | Пространство имён пользовательских интерфейсов. |
| [UrlPreview](/api_d7/bitrix/main/urlpreview/index.php) | Пространство имён для работы с "богатыми ссылками". |
| [UrlRewriterRuleMaker](/api_d7/bitrix/main/urlrewriterrulemaker/index.php) | Класс для работы с правилами переадресации. |
| [UserConsent](/api_d7/bitrix/main/userconsent/index.php) | Пространство имён для работы с соглашениями пользователей. |
| [UserField](/api_d7/bitrix/main/userfield/index.php) | Пространство имён для классов и событий Пользовательских полей. |
| [UserTable](/api_d7/bitrix/main/usertable/index.php) | Класс для работы с пользователями. |
| [UserUtils](/api_d7/bitrix/main/userutils/index.php) | Класс утилит для работы с пользователями. |
| [Web](/api_d7/bitrix/main/web/index.php) | Пространство имён для классов, работающих с WEB. |
| [XmlWriter](/api_d7/bitrix/main/xmlwriter/index.php) | класс для экспорта в XML. |
| Классы для работы с ошибками | |
| [Error](/api_d7/bitrix/main/error/index.php) | Класс ошибок. |
| [ErrorCollection](/api_d7/bitrix/main/errorcollection/index.php) | Коллекция ошибок. |
| Классы для работы с исключениями | |
| [SystemException](/api_d7/bitrix/main/systemexception/index.php) | Базовый класс фатальных исключений. |
| [ArgumentException](/api_d7/bitrix/main/argumentexception/index.php) | Исключение выводится когда аргумент функции не валидный |
| [ArgumentNullException](/api_d7/bitrix/main/argumentnullexception/index.php) | Исключение выводится когда передаётся пустое значение в метод который не принимает такого значения как валидное. |
| [ArgumentOutOfRangeException](/api_d7/bitrix/main/argumentoutofrangeexception/index.php) | Исключение выводится когда значение аргумента находится вне допустимого диапазона значений. |
| [ArgumentTypeException](/api_d7/bitrix/main/argumenttypeexception/index.php) | Исключение выводится, когда тип аргумента не принимается функцией. |
| [ObjectNotFoundException](/api_d7/bitrix/main/objectnotfoundexception/index.php) | Исключение выводится когда отсутствует объект. |
| [ObjectException](/api_d7/bitrix/main/objectexception/index.php) | Исключение выводится, когда объект не может быть создан. |
| [ObjectPropertyException](/api_d7/bitrix/main/objectpropertyexception/index.php) | Исключение выводится когда свойство объекта не валидно. |
| InvalidOperationException | Исключение выводится когда вызываемый метод не является валидным для текущего состояния объекта. |
| [NotSupportedException](/api_d7/bitrix/main/notsupportedexception/index.php) | Исключение выводится когда операция не поддерживается. |
| [NotImplementedException](/api_d7/bitrix/main/notimplementedexception/index.php) | Исключение выводится, когда операция не осуществлена, хотя должна была быть выполнена. |

Новинки документации в соцсетях:
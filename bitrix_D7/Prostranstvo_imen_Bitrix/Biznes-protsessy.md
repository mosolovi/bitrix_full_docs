[Пространство имён Bitrix](/api_d7/bitrix/index.php)

Бизнес-процессы (с версии 15.6.0)

Бизнес-процессы
===============

**Бизнес-процессы** - модуль для создания и работы с бизнес-процессами

Перед использованием модуля необходимо проверить установлен ли он, и подключить его при помощи конструкции:

```
\Bitrix\Main\Loader::includeModule('bizproc');
Копировать
```

| Класс | Описание | С версии |
| --- | --- | --- |
| [BaseType](/api_d7/bitrix/bizproc/basetype/index.php) | Набор обработчиков базовых типов данных в бизнес-процессах. |  |
| [FieldType](/api_d7/bitrix/bizproc/fieldtype/index.php) | Вспомогательный класс для работы API типов полей. |  |
| [RestActivityTable](/api_d7/bitrix/bizproc/restactivitytable/index.php) | Стандартная ORM-таблица для хранения и управления данными REST действий. |  |
| [RestService](/api_d7/bitrix/bizproc/restservice/index.php) | API для работы бизнес-процессов через REST. |  |
| [Activity](/api_d7/bitrix/bizproc/activity/index.php) | Пространство имен, содержащее классы для работы с действиями. | 17.0.0 |

  

#### Смотрите также:

* [Учебный курс "Бизнес-процессы"](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=57)
* [Бизнес-процессы (API для старой версии ядра)](http://dev.1c-bitrix.ru/api_help/bizproc/index.php)
* [урок "Автоматический запуск бизнес-процессов и роботов"](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=57&LESSON_ID=20686)

Новинки документации в соцсетях:
[Пространство имён Bitrix](/api_d7/bitrix/index.php)

Конверсия (с версии 15.5.0)

Конверсия
=========

Модуль **Конверсия** позволяет не только вычислить конверсию для любого выбранного целевого действия, но и получить отчет, позволяющий понять, что влияет на ее значение и как ее можно улучшить.

Перед использованием модуля необходимо проверить установлен ли он, и подключить его при помощи конструкции:

```
\Bitrix\Main\Loader::includeModule(
	'conversion'
);Копировать
```

| Класс | Описание | С версии |
| --- | --- | --- |
| [Internals](/api_d7/bitrix/conversion/internals/index.php) | Пространство имён содержит классы для работы с основными сущностями модуля. | 15.5.1 |
| [DayContext](/api_d7/bitrix/conversion/daycontext/index.php) | Класс для работы с уникальным ежедневным контекстом. |  |
| [MobileDetect](/api_d7/bitrix/conversion/mobiledetect/index.php) | Класс для работы с контекстом мобильных устройств. |  |

  

#### Смотрите также

* [Конверсия (API для старой версии ядра)](http://dev.1c-bitrix.ru/api_help/conversion/index.php)
* [Конверсия (учебный курс)](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=41&CHAPTER_ID=07212)

Новинки документации в соцсетях:
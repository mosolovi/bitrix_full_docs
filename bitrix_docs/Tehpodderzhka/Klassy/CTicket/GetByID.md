[Техподдержка](/api_help/support/index.php)

[Классы](/api_help/support/classes/index.php)

[CTicket](/api_help/support/classes/cticket/index.php)

GetByID (3.0.1)

GetByID
=======

Включить вкладки

Описание и параметры

Пример

### Описание и параметры

```
record set
CTicket::GetByID(
	int ID,
	char(2) lang=LANG,
	char(1) CHECK_RIGHTS="Y",
	char(1) get_user_name="Y",
	char(1) get_dictionary_name="Y"
);Копировать
```

Метод возвращает данные по одному обращению. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| **ID** | ID обращения. |  |
| **lang** | Двухсимвольный код языка в формате которого необходимо выбрать временные параметры обращения (время создания, изменения, закрытия); необязательный параметр, по умолчанию - код текущего сайта. |  |
| **CHECK\_RIGHTS** | Необязательный параметр. "Y" - будут выбраны только те обращения которые текущий пользователь может просматривать (по умолчанию); "N" - выбирать все обращения независимо от прав текущего пользователя. Изменен на **checkRights** c 12.0.0 | 3.3.9 |
| **get\_user\_name** | Необязательный параметр. "Y" - при выборке обращений будут также выбраны такие поля как OWNER\_LOGIN, OWNER\_NAME, RESPONSIBLE\_LOGIN, RESPONSIBLE\_NAME, MODIFIED\_LOGIN, MODIFIED\_NAME, LAST\_MESSAGE\_LOGIN, LAST\_MESSAGE\_NAME, CREATED\_LOGIN, CREATED\_EMAIL, CREATED\_NAME, описывающие параметры пользователей имевших отношение к данному обращению (по умолчанию); "N" - вышеперечисленные поля не будут выбраны, но зато это ускорит работу метода. | 3.3.15 |
| **get\_dictionary\_name** | Необязательный параметр. "Y" - при выборке обращений будут также выбраны такие поля как CATEGORY\_NAME, CATEGORY\_SID, CRITICALITY\_NAME, CRITICALITY\_SID, STATUS\_NAME, STATUS\_SID, MARK\_NAME, MARK\_SID, SOURCE\_NAME, SOURCE\_SID, описывающие поля из справочника техподдержки (по умолчанию); "N" - вышеперечисленные поля не будут выбраны, но зато это ускорит работу метода. Удален с 4.0.6 | 3.3.15 |
| bAdmin | Необязательный параметр. Значение по умолчанию - "N". |  |
| get\_extra\_names | Необязательный параметр. Значение по умолчанию - "Y". | 4.0.6 |
| arParams | Необязательный параметр. | 12.0.0 |

### Пример

#### Пример массива одной строки выборки, возвращаемой методом CTicket::GetByID

```
Array
(
	[ID] => 647
	[LID] => ru
	[DATE_CREATE] => 17.03.2004 15:27:05
	[TIMESTAMP_X] => 19.04.2004 13:37:30
	[DATE_CLOSE] => 
	[AUTO_CLOSED] => 
	[AUTO_CLOSE_DAYS] => 
	[CATEGORY_ID] => 27
	[CRITICALITY_ID] => 8
	[STATUS_ID] => 14
	[MARK_ID] => 21
	[SOURCE_ID] => 
	[TITLE] => Импорт-экспорт в торговый каталог
	[MESSAGES] => 30
	[OWNER_USER_ID] => 166
	[OWNER_GUEST_ID] => 14649
	[OWNER_SID] => 
	[CREATED_USER_ID] => 166
	[CREATED_GUEST_ID] => 14649
	[CREATED_MODULE_NAME] => support
	[RESPONSIBLE_USER_ID] => 12
	[MODIFIED_USER_ID] => 166
	[MODIFIED_GUEST_ID] => 16218
	[MODIFIED_MODULE_NAME] => support
	[LAST_MESSAGE_USER_ID] => 166
	[LAST_MESSAGE_GUEST_ID] => 16218
	[LAST_MESSAGE_SID] => 
	[SUPPORT_COMMENTS] => 
	[OWNER_LOGIN] => ant
	[OWNER_EMAIL] => mail@server.com
	[OWNER_NAME] => Поручик Лукаш
	[RESPONSIBLE_LOGIN] => wizard
	[RESPONSIBLE_EMAIL] => mail@server.com
	[RESPONSIBLE_NAME] => Фельдкурат Кац
	[MODIFIED_LOGIN] => ant
	[MODIFIED_EMAIL] => mail@server.com
	[MODIFIED_NAME] => Поручик Лукаш
	[LAST_MESSAGE_LOGIN] => ant
	[LAST_MESSAGE_EMAIL] => mail@server.com
	[LAST_MESSAGE_NAME] => Поручик Лукаш
	[CREATED_LOGIN] => ant
	[CREATED_EMAIL] => mail@server.com
	[CREATED_NAME] => Поручик Лукаш
	[CATEGORY_NAME] => Установка и настройка
	[CATEGORY_DESC] => 
	[CATEGORY_SID] => 
	[CRITICALITY_NAME] => Средняя
	[CRITICALITY_DESC] => 
	[CRITICALITY_SID] => middle
	[STATUS_NAME] => В стадии решения
	[STATUS_DESC] => 
	[STATUS_SID] => 
	[MARK_NAME] => Ответ устраивает
	[MARK_DESC] => 
	[MARK_SID] => 
	[SOURCE_NAME] => 
	[SOURCE_DESC] => 
	[SOURCE_SID] => 
	[LAMP] => yellow
)Копировать
```

Новинки документации в соцсетях:
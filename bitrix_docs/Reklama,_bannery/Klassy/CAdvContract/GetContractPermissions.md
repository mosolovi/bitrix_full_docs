[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvContract](/api_help/advertising/classes/cadvcontract/index.php)

GetContractPermissions (3.3.14)

GetContractPermissions
======================

Включить вкладки

Описание и параметры

Пример

### Описание и параметры

```
text
CAdvContract::GetContractPermissions(
	int CONTRACT_ID
);Копировать
```

Метод возвращает права всех пользователей по заданному контракту. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| CONTRACT\_ID | ID контракта. |

### Пример

#### Пример массива, возвращаемого методом

```
Array
(
	[VIEW] => Array
		(
			[0] => Array
				(
					[USER_ID] => 341
					[USER_LOGIN] => view
					[USER_NAME] => Сергей
					[USER_LAST_NAME] => Рыжиков
					[USER_EMAIL] => mail@server.com
				)
			[1] => Array
				(
					[USER_ID] => 340
					[USER_LOGIN] => edit
					[USER_NAME] => Анна
					[USER_LAST_NAME] => Долгова
					[USER_EMAIL] => mail@server.com
				)
			[2] => Array
				(
					[USER_ID] => 2
					[USER_LOGIN] => nessy
					[USER_NAME] => Vitaly
					[USER_LAST_NAME] => Kaplich
					[USER_EMAIL] => nessy@bitrix.bx
				)
		)
	[ADD] => Array
		(
			[0] => Array
				(
					[USER_ID] => 342
					[USER_LOGIN] => add
					[USER_NAME] => Андрей
					[USER_LAST_NAME] => 
					[USER_EMAIL] => mail@server.com
				)
			[1] => Array
				(
					[USER_ID] => 340
					[USER_LOGIN] => edit
					[USER_NAME] => Анна
					[USER_LAST_NAME] => Долгова
					[USER_EMAIL] => mail@server.com
				)
			[2] => Array
				(
					[USER_ID] => 2
					[USER_LOGIN] => nessy
					[USER_NAME] => Vitaly
					[USER_LAST_NAME] => Kaplich
					[USER_EMAIL] => nessy@bitrix.bx
				)
		)
	[EDIT] => Array
		(
			[0] => Array
				(
					[USER_ID] => 340
					[USER_LOGIN] => edit
					[USER_NAME] => Анна
					[USER_LAST_NAME] => Долгова
					[USER_EMAIL] => mail@server.com
				)
			[1] => Array
				(
					[USER_ID] => 2
					[USER_LOGIN] => nessy
					[USER_NAME] => Vitaly
					[USER_LAST_NAME] => Kaplich
					[USER_EMAIL] => nessy@bitrix.bx
				)
		)
)Копировать
```

Новинки документации в соцсетях:

© «Битрикс», 2001-2025, «1С-Битрикс», 2025

Наверх
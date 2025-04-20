[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvContract](/api_help/advertising/classes/cadvcontract/index.php)

GetUserPermissions (3.3.14)

GetUserPermissions
==================

```
text
CAdvContract::GetUserPermissions(
	int USER_ID=false
	CONTRACT_ID=0
);Копировать
```

Метод возвращает массив прав заданного пользователя по всем контрактам. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| USER\_ID | ID пользователя; если не определён - используется ID текущего пользователя. Необязательный параметр. |
| CONTRACT\_ID | Необязательный параметр. |

#### Пример массива, возвращаемого методом

```
Array
(
	[34] => Array
		(
			[0] => ADD
			[1] => VIEW
			[2] => EDIT
		)
	[52] => Array
		(
			[0] => ADD
			[1] => VIEW
		)
)Копировать
```

Индексом массива является ID контракта.
Значением - массив прав на данный контракт.

Новинки документации в соцсетях:
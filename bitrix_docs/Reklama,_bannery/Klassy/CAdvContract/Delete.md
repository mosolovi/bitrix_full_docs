[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvContract](/api_help/advertising/classes/cadvcontract/index.php)

Delete (3.3.4)

Delete
======

```
boolean
CAdvContract::Delete(
	int CONTRACT_ID,
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод удаляет контракт и все баннеры, к нему привязанные. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| CONTRACT\_ID | ID контракта. |
| CHECK\_RIGHTS | "Y" - необходимо проверить право на удаление у текущего пользователя; "N" - прав проверять не надо. Необязательный параметр. |

Новинки документации в соцсетях:
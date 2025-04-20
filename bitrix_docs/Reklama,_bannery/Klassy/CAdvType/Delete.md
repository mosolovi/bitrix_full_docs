[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvType](/api_help/advertising/classes/cadvtype/index.php)

Delete (3.3.4)

Delete
======

```
boolean
CAdvType::Delete(
	varchar(255) TYPE_SID,
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод удаляет тип баннеров и все баннеры, к нему привязанные. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| TYPE\_SID | Символьный идентификатор типа. |
| CHECK\_RIGHTS | "Y" - необходимо проверить право на удаление у текущего пользователя; "N" - прав проверять не надо. Необязательный параметр. |

Новинки документации в соцсетях:
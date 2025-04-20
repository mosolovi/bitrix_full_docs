[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogPost](/api_help/blogs/classes/cblogpost/index.php)

Delete (5.0.2)

Delete
======

```
bool
CBlogPost::Delete(
	int ID
);Копировать
```

Метод удаляет сообщение *ID* и все объекты, с ним связанные. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сообщения. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления сообщения, в противном случае возвращает *false*.

#### Примеры использования

```
<?
$DB->StartTransaction();
if(!CBlogPost::Delete($ID))
{
	echo 'Ошибка удаления сообщения '.$ID;
	$DB->Rollback();
}
else
	$DB->Commit();
?>Копировать
```

Новинки документации в соцсетях:
[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)

Delete (5.9.1)

Delete
======

```
bool
CBlogSitePath::Delete(
	int ID
);Копировать
```

Метод удаляет путь с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор пути. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления пути, в противном случае возвращает *false*.

#### Примеры использования

```
<?
$ID = 1;
if(!CBlogSitePath::Delete($ID))
{
	echo 'Ошибка удаления пути '.$ID;
}
else
	echo 'Путь удален.';
?>Копировать
```

Новинки документации в соцсетях:
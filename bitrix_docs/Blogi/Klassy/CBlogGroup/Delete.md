[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogGroup](/api_help/blogs/classes/cbloggroup/index.php)

Delete (7.1.2)

Delete
======

```
bool
CBlogGroup::Delete(
	int ID
);Копировать
```

Метод удаляет группу с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор группы. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления группы, в противном случае возвращает *false*.

#### Примеры использования

```
<?
if(!CBlogGroup::Delete($ID))
{
	echo 'Ошибка удаления группы '.$ID;
}
else
	echo 'Группа удалена.';
?>Копировать
```

Новинки документации в соцсетях:
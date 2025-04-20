[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogCategory](/api_help/blogs/classes/cblogcategory/index.php)

Delete (6.5.1)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CBlogCategory::Delete(
	int ID
);Копировать
```

Метод удаляет категорию с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор категории. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления категории, в противном случае возвращает *false*.

### Примеры использования

```
<?
if(!CBlogCategory::Delete($ID))
{
	echo 'Ошибка удаления категории '.$ID;
}
else
	echo 'Категория удалена.';
?>Копировать
```

Удаление всех тэгов блога:

```
CModule::IncludeModule ("blog");
$dbCategory = CBlogCategory::GetList (Array ("ID" => "ASC"), Array ("BLOG_ID" => 5));
while ($arCategory = $dbCategory->Fetch())
{
	CBlogCategory::Delete ($arCategory["ID"]);
}Копировать
```

Новинки документации в соцсетях:
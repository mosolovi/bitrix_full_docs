[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnIBlockDelete (доступно с 3.2.1)

OnIBlockDelete
==============

```
функция-обработчик(
	int ID 
);Копировать
```

Вызывается в момент удаления информационного блока.

#### Параметры

| Параметр | Описание |
| --- | --- |
| ID | ID информационного блока. |

#### Примеры использования

```
<?
// Подключаем к событию обработчик
RegisterModuleDependences(
	"iblock", 
	"OnIBlockDelete", 
	"catalog", 
	"CCatalog", 
	"OnIBlockDelete"
);
// Реализуем обработчик
class CCatalog
{
	* * *
	public static function OnIBlockDelete($ID)
	{
		return CCatalog::Delete($ID);
	}
}
// Теперь при удалении блока будет вызываться обработчик
?>Копировать
```

Новинки документации в соцсетях:
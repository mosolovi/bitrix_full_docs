[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockDelete (доступно с 3.3.8)

OnBeforeIBlockDelete
====================

```
bool
функция-обработчик(
	int ID 
);Копировать
```

Вызывается перед удалением информационного блока.

#### Параметры

| Параметр | Описание |
| --- | --- |
| ID | ID информационного блока. |

#### Возвращаемое значение

Обработчик должен вернуть false в случае если необходимо отменить удаление информационного блока.

#### Примеры использования

```
<?
// Подключаем к событию обработчик
RegisterModuleDependences(
	"iblock", 
	"OnBeforeIBlockDelete", 
	"catalog", 
	"CCatalog", 
	"OnIBlockDelete"
);
// Реализуем обработчик
class CCatalog
{
	* * *
	public static function OnBeforeIBlockDelete($ID)
	{
		return false;
	}
}
// Теперь нельзя удалить информационный блок.
?>Копировать
```

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnIBlockElementDelete (доступно с 3.1.3)

OnIBlockElementDelete
=====================

```
функция-обработчик(
	int ID 
);Копировать
```

Вызывается в момент удаления элемента информационного блока.

**Примечание:** начиная с версии 15.5.12, событие вызывается до удаления из таблиц любых данных, связанных с элементом.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *ID* | ID элемента информационного блока. |

#### Примеры использования

```
<?
// Подключаем к событию обработчик
RegisterModuleDependences(
	"iblock", 
	"OnIBlockElementDelete", 
	"catalog", 
	"CCatalogProduct", 
	"OnIBlockElementDelete"
);
// Реализуем обработчик
class CCatalogProduct
{
	* * *
	public static function OnIBlockElementDelete($PRODUCT_ID)
	{
		global $DB;
		echo "Удаляем...";
		return True;
	}
}
// Теперь при удалении элемента будет вызываться обработчик
?>Копировать
```

Новинки документации в соцсетях:
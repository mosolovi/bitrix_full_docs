[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

GetUIFilterProperty (с версии 18.5.0)

GetUIFilterProperty
===================

```
result_type
public static function GetUIFilterProperty(
	$property,
	$strHTMLControlName,
	&$fields
);Копировать
```

Метод описывает вид поля фильтрации в компоненте
main.ui.filter



Компонент системный и не документируется.   
 В административном разделе отвечает за вывод фильтра в новом гриде.   
 ![](/upload/api_help/main/main_ui_filter_ib.png)
на административных страницах Инфоблоков.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| strHTMLControlName | Массив, описывающий свойство данного типа. |
| property | Массив данных по форме. |
| $fields | Массив, описание поля для фильтра. Передаётся по ссылке. |

#### Примеры использования

Пример описания выпадающего списка

```
{
	// значения выпадающего списка
	$items = [
		'ИД_1' => 'значение_1',
		...
		'ИД_N' => 'значение_N',
	];
	//ИД могут быть как целыми числами, так и строками
	$fields['type'] = 'list';
	$fields['items'] = $items;
	$fields['filterable'] = '';
	// если нужен множественный выбор, добавить еще строчку
	$fields['params'] = ['multiple' => 'Y'];
}Копировать
```

Новинки документации в соцсетях:
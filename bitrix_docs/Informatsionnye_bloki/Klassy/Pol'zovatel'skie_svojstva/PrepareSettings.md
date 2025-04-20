[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

PrepareSettings (доступен с 8.6.1)

PrepareSettings
===============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CIBlockProperty*::PrepareSettings(
	array arFields
);Копировать
```

Метод возвращает либо массив с дополнительными настройками свойства, либо весь набор настроек, включая стандартные. Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

**Примечание №1:** до версии модуля Информационные блоки **12.5.7** метод возвращает только массив с дополнительными настройками свойства.

**Примечание №2:** вызывается перед сохранением метаданных свойства в базу данных.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arFields | Значения полей метаданных свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |

#### Возвращаемое значение

Строка или массив. Если метод возвращает весь набор настроек, то в этом случае дополнительные настройки передаются в ключе *USER\_TYPE\_SETTINGS* в виде массива.

### Смотрите также

* [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty)
* [GetUserTypeDescription](/api_help/iblock/classes/user_properties/GetUserTypeDescription.php)

### Примеры использования

Без модификации основных полей свойства

```
class CIBlockPropertyMyDateTime
{
	public static function PrepareSettings($arFields): array
	{
		$fields = [];
		if (isset($arFields['USER_TYPE_SETTINGS']) && is_array($arFields['USER_TYPE_SETTINGS']))
		{
			$fields = $arFields['USER_TYPE_SETTINGS'];
		}
		$width = (int)($fields['WIDTH'] ?? 0);
		if ($width <= 0)
		{
			$width = 100;
		}
		$height = (int)($fields['HEIGHT'] ?? 0);
		if ($height <= 0)
		{
			$height = 100;
		}
        
		return [
			'WIDTH' => $width,
			'HEIGHT' => $height
		];
	}
}Копировать
```

С модификацией основных полей:

```
class CIBlockPropertyMyDate
{
	public static function PrepareSettings($fields): array
	{
		$userSettings = [];
		if (isset($fields['USER_TYPE_SETTINGS']) && is_array($fields['USER_TYPE_SETTINGS']))
		{
			$userSettings = $fields['USER_TYPE_SETTINGS'];
		}
		$userSettings['WIDTH'] = (int)($userSettings['WIDTH'] ?? 0);
		if ($userSettings['WIDTH'] <= 0)
		{
			$userSettings['WIDTH'] = 100;
		}
		$userSettings['HEIGHT'] = (int)($userSettings['HEIGHT'] ?? 0);
		if ($userSettings['HEIGHT'] <= 0)
		{
			$userSettings['HEIGHT'] = 100;
		}
		$fields['MULTIPLE'] = 'N'; // запрещаем множественность свойства
		$fields['USER_TYPE_SETTINGS'] = $userSettings;
		return $fields;
	}
}Копировать
```

Новинки документации в соцсетях:
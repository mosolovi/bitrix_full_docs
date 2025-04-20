[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormValidator](/api_help/form/classes/cformvalidator/index.php)

GetAllList (6.0.0)

GetAllList
==========

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
CDBResult
CFormValidator::GetAllList(
	mixed arFilter = array(),
)Копировать
```

Возвращает список зарегистрированных валидаторов в виде объекта класса [CDBResult](/api_help/main/reference/cdbresult/index.php). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *arFilter* | Массив для фильтрации. Необязательный параметр. В массиве допустимы следующие ключи:  * **TYPE** - список типов полей; |

### Пример использования

```
if (CModule::IncludeModule("form"))
{
	$arFilter = array("TYPE" => array("text", "textarea"));
  
	$sType = "<b>".implode("</b>, <b>", $arFilter["TYPE"])."</b>";
	$rsValidators = CFormValidator::GetAllList($arFilter);
	if ($rsValidators->SelectedRowsCount() > 0)
	{
		echo "Найденные валидаторы для полей типа ".$sType.":<ul>";
		while ($arValidator = $rsValidators->GetNext())
		{
			echo "<li>[".$arValidator["NAME"]."] ".$arValidator["DESCRIPTION"]."</li>";
		}
		echo "</ul>";
	}
	else
	{
		echo "Валидаторов, применимых к полям типа ".$sType." не обнаружено.";
	}
}
else
{
	ShowError('Модуль веб-форм не установлен');
}Копировать
```

Новинки документации в соцсетях:
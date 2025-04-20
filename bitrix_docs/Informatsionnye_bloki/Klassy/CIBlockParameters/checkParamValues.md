[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockParameters](/api_help/iblock/classes/ciblockparameters/index.php)

checkParamValues (доступно с 14.5.10)

checkParamValues
================

```
CIBlockParameters::checkParamValues(
	$value
);Копировать
```

Проверяет значение параметра. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| value | Проверяемое значение |

#### Возвращаемое значение

Возвращает *true*, если значение не может быть приведено к *false*.

#### Примеры использования

```
$arCodes = array('', 0, 'ARTICUL');
$arCodes = array_filter($arCodes, 'CIBlockParameters::checkParamValues');Копировать
```

После этого в $arCodes будет выглядеть так:

```
$arCodes = array(2 => 'ARTICUL');Копировать
```

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)

isExistsMnemonicCode (с версии 21.300.100)

isExistsMnemonicCode
====================

```
bool
public function CIBlockSection::isExistsMnemonicCode(
	string $code,
	?int $sectionId,
	int $iblockId
);Копировать
```

Нестатический метод проверки существования символьного кода. Возвращаемое значение - *true / false* (уже существует или нет).

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| $code | Непустая строка символьного кода, для которой выполняется поиск, Тип - строка (string), обязательный |
| $sectionId | Идентификатор раздела. Тип - целое число (int) или null, обязательный. Если указать не null - в фильтр будет добавлено условие по ID записи |
| $iblockId | Идентификатор инфоблока. Тип - целое число (int), обязательный. |

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

getPublicElementsOrmFilter (с версии 21.300.100)

getPublicElementsOrmFilter
==========================

```
array
public static function CIBlockElement::getPublicElementsOrmFilter(
	array $filter
);Копировать
```

Статический метод для дополнения фильтра orm на основе массива. Служит для получения фильтра, отсекающего неопубликованные записи в режиме документооборота (историю редактирования).

Возвращаемое значение - массив.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| $filter | Массив фильтра для orm ([\Bitrix\Iblock\ElementTable::getList](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=5753)) |

Новинки документации в соцсетях:
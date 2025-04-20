[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)

GetSectionElementsCount (доступен с 3.2.1)

GetSectionElementsCount
=======================

```
int CIBlockSection::GetSectionElementsCount(
	int ID,
	array arFilter = Array()
);Копировать
```

Метод считает количество элементов внутри раздела *ID*, учитывая фильтр *arFilter*. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код раздела. |
| arFilter | Массив вида Array("фильтруемое поле"=>"значение", ...), где фильтруемое поле может принимать значения:   *CNT\_ACTIVE* - активные элементы (Y|N),*CNT\_ALL* - учитывать ещё не опубликованные элементы (если установлен модуль документооборота), *PROPERTY* - массив для фильтрации элементов по значениям свойств, вида Array("код свойства"=>"значение", ...), |

**Примечание:** метод устарел, для получения количества рекомендуется использовать метод [CIBlockElement::GetList](/api_help/iblock/classes/ciblockelement/getlist.php) с установленным параметром для группировки.

#### Смотрите также

* [CIBlockElement::GetList](/api_help/iblock/classes/ciblockelement/getlist.php)

Новинки документации в соцсетях:
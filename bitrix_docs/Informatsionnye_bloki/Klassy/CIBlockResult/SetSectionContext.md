[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)

SetSectionContext (доступен с 7.1.3)

SetSectionContext
=================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
void
CIBlockResult::SetSectionContext(
	array arSection
);Копировать
```

Метод устанавливает поля раздела в качестве родителя элемента для подстановки в шаблоны путей методом [CIBlockResult::GetNext](/api_help/iblock/classes/ciblockresult/getnext.php). Если родительский раздел не определен с помощью вызова этого метода, то для подстановки шаблона будут использованы поля из раздела с минимальным ID к которому привязан элемент. Нестатический метод.

**Примечание**: Используется в компонентах для сохранения текущего просматриваемого пользователем раздела в случае множественной привязки элементов.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arSection | Массив полей раздела поля которого будут использованы для подстановки значений в шаблон пути. |

#### Возвращаемое значение

Метод ничего не возвращает.

### Смотрите также

* [CIBlockResult::GetNext](/api_help/iblock/classes/ciblockresult/getnext.php)
* [CIBlockResult::](/api_help/iblock/classes/ciblockresult/getnext.php)[SetUrlTemplates](/api_help/iblock/classes/ciblockresult/seturltemplates.php)

### Примеры использования

```
<?
$rsElements = CIBlockElement::GetList(array(), array("ID" => $ID), false, false, array("ID", "NAME", "DETAIL_PAGE_URL"));
$rsElements->SetUrlTemplates("/catalog/#SECTION_CODE#/#ELEMENT_CODE#.php");
$rsElements->SetSectionContext($arSection);
$arElement = $rsElements->GetNext();
?>Копировать
```

Новинки документации в соцсетях:
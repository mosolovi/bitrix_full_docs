[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

CounterInc (доступен с 3.3.8)

CounterInc
==========

```
CIBlockElement::CounterInc(
	int ID
);Копировать
```

Увеличивает счетчик просмотров элемента с кодом *ID*.
При увеличении учитывается уникальность просмотров данного элемента в одной сессии. Метод статический. Метод не сбрасывает тегированый кеш.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код элемента. |

#### Примеры использования

```
<?
if(CModule::IncludeModule("iblock"))
	CIBlockElement::CounterInc($ID);
?>Копировать
```

Новинки документации в соцсетях:
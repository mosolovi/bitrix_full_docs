[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

SetPropertyValueCode (доступен с 3.0.13)

SetPropertyValueCode
====================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CIBlockElement::SetPropertyValueCode(
	int ELEMENT_ID,
	string PROPERTY_CODE,
	string PROPERTY_VALUE
);Копировать
```

Метод изменяет значение свойства элемента информационного блока. Выполняет один дополнительный запрос к БД для определения кода информационного блока элемента. Если код инфоблока известен, то лучше воспользоваться функцией [SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php), задав ей 4-й параметр. Статический метод.

**Внимание!** Удалять и обновлять несколько значений файлового свойства можно только ОДНИМ вызовом, а не несколькими, так как меняются ID значений свойств.

Отличие метода от SetPropertyValuesEx в том, что он не перезаписывает множественное свойства типа Файл, а дополняет.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ELEMENT\_ID | Код элемента, значение свойства которого изменяется. |
| PROPERTY\_CODE | Символьный или числовой код свойства, которое изменяется. Если передан неверный PROPERTY\_CODE метод все равно вернет *true*. |
| PROPERTY\_VALUE | Значение свойства (одиночное или множественное в виде массива значений). Если для свойства типа **список**, **привязка к элементам или разделам** (и их клонам) будет установлено равным переданному значению PROPERTY\_VALUE, без проверки, метод вернет *true*. (Если передавать значение, а не его ENUM\_ID, то в БД будет записано само значение, привязки к значению не будет.) |

#### Возвращаемое значение

При успешном изменении вернет *true*, иначе - *false*.

### Смотрите также

* [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php)
* [CIBlockElement::SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php)

### Примеры использования

**Пример 1:**

```
<?
$arFile = CFile::MakeFileArray($_SERVER["DOCUMENT_ROOT"]."/images/add_basket.gif");
CIBlockElement::SetPropertyValueCode($ELEMENT_ID, "picture", $arFile);
?>Копировать
```

При добавлении/изменении значений свойства можно одновременно установить и описание, если после вызова *MakeFileArray* добавить "description".

**Пример 2:**

Для обновления значения поля типа html/текст значение TYPE должно быть либо HTML, либо TEXT:

```
CIBlockElement::SetPropertyValueCode(ELEMENT_ID, NAME_PROPERTY, array(array("TYPE"=>"TEXT", "TEXT"=>"мой текст")));
Копировать
```

Новинки документации в соцсетях:
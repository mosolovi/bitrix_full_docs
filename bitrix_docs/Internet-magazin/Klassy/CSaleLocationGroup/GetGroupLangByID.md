[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocationGroup](/api_help/sale/classes/csalelocationgroup/index.php)

GetGroupLangByID (доступен с 3.2.2, устарел с 15.0.0)

GetGroupLangByID
================

Включить вкладки

Описание и параметры

Возвращаемые значения

Пример использования

Метод устарел. Рекомендуется использовать методы класса `\Bitrix\Sale\Location\GroupTable`.

### Описание и параметры

```
array
CSaleLocationGroup::GetGroupLangByID(
	int ID,
	string strLang = LANGUAGE_ID
);Копировать
```

Метод возвращает языкозависимые параметры группы местоположений с кодом ID для языка с кодом strLang. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код группы местоположений. |
| strLang | Код языка. |

### Возвращаемые значения

Возвращается ассоциативный массив с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код записи. |
| LOCATION\_GROUP\_ID | Код группы местоположений. |
| NAME | Название группы. |
| LID | Язык названия. |

### Пример использования

```
<?
$arGroupLang = CSaleLocationGroup::GetGroupLangByID(2, "en");
echo $arGroupLang["NAME"];
?>Копировать
```

Новинки документации в соцсетях:
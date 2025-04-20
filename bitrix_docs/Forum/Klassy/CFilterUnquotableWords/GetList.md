[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CFilterUnquotableWords](/api_help/forum/developer/cfilterunquotablewords/index.php)

GetList

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
CDBResult
GetList(
	[array arOrder [,
	array arFilter [,
	bool bCount ]]]
);Копировать
```

Возвращает список записей по фильтру *arFilter*, отсортированый в соответствии с *arOrder*. Метод нестатический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| arOrder | Массив вида Array(*by1*=>*order1*[, *by2*=>*order2* [, ..]]), где     *by* - поле для сортировки, может принимать значения       *ID* - ID сообщения;       *WORDS* - слово;       *PATTERN* - шаблон;       *REPLACEMENT* - замена;       *DESCRIPTION* - описание;       *USE\_IT* - использовать этот шаблон в фильтре;     *order* - порядок сортировки, может принимать значения       *ASC* - по возрастанию;       *DESC* - по убыванию;     Необязательный. По умолчанию равен Array("ID"=>"ASC") | 5.1.0 |
| arFilter | массив вида array("фильтруемое поле"=>"значения фильтра" [, ...])   "фильтруемое поле" может принимать значения       *ID* - ID сообщения;       *DICTIONARY\_ID* - ID словаря;       *WORDS* - слово;       *PATTERN* - шаблон;       *REPLACEMENT* - замена;       *DESCRIPTION* - описание;       *USE\_IT* - использовать этот шаблон в фильтре;     фильтруемое поле может содержать перед названием тип проверки фильтра   "!" - не равно   "<" - меньше   "<=" - меньше либо равно   ">" - больше   ">=" - больше либо равно     Обязательное. | 5.1.0 |
| bCount | Если параметр равен True, то возвращается только количество сообщений, которое соответствует установленному фильтру. Необязательный. По умолчанию равен False. | 5.1.0 |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* таблица ["Словарь"](/api_help/forum/fields.php#cfilterdictionary)
* таблица ["Словарь букв"](/api_help/forum/fields.php#cfilterletter)
* таблица ["Словарь слов"](/api_help/forum/fields.php#cfilterunquotablewords)

Новинки документации в соцсетях:
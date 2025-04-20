[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

GetElementGroups (доступен с 3.1.3)

GetElementGroups
================

Включить вкладки

Описание

Параметры вызова

Примеры использования

### Описание

```
CDBResult
CIBlockElement::GetElementGroups(
	mixed ID,
	bool bElementOnly = false,
	array arSelect = array()
);Копировать
```

Принимает массив идентификаторов элементов. Возвращает группы, которым принадлежит элемент, по его коду *ID*. Метод статический.

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля раздела](/api_help/iblock/fields.php#fsection)
* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[SetElementSectio](/api_help/iblock/classes/ciblockelement/setelementsection.php)[n()](/api_help/iblock/classes/ciblockelement/setelementsection.php)

### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | ID элемента, либо массив ID элементов, для которых надо вернуть привязки к разделам. |  |
| *bElementOnly* | Не обязательный параметр. Указывает на необходимость выборки привязок и из свойств типа "Привязка к разделу". По умолчанию равен false и значения свойств будут выбраны. Если значения свойств не нужны, то значением параметра надо задать true. | 5.1.0 |
| *arSelect* | Перечень возвращаемых полей. Допустимые поля: Поля, относящиеся к разделу:   * ID - ID раздела инфоблока; * TIMESTAMP\_X - дата последнего изменения параметров раздела; * MODIFIED\_BY - идентификатор пользователя, в последний раз изменившего раздел; * DATE\_CREATE - дата создания раздела; * CREATED\_BY - идентификатор пользователя, создавшего раздел; * IBLOCK\_ID - ID информационного блока; * IBLOCK\_SECTION\_ID - ID раздела-родителя; * ACTIVE - (Y|N) флаг активности раздела; * GLOBAL\_ACTIVE - (Y|N) флаг активности раздела, учитывая активность вышележащих (родительских) разделов; * SORT - порядок сортировки; * NAME - название раздела; * PICTURE - код картинки раздела; * LEFT\_MARGIN - левая граница раздела; * RIGHT\_MARGIN - правая граница раздела; * DEPTH\_LEVEL - уровень вложенности раздела; * DESCRIPTION - описание раздела; * DESCRIPTION\_TYPE - тип описания группы (text/html); * SEARCHABLE\_CONTENT - содержимое для поиска при фильтрации групп; * CODE - символьный идентификатор; * XML\_ID - внешний код; * EXTERNAL\_ID - внешний код; * TMP\_ID - временный строковый идентификатор, используемый для служебных целей; * DETAIL\_PICTURE - код картинки детального просмотра раздела; * SOCNET\_GROUP\_ID - группа Социальной сети.   Поля, относящиеся к инфоблоку раздела:   * LIST\_PAGE\_URL - шаблон URL-а к странице для публичного просмотра списка элементов информационного блока; * SECTION\_PAGE\_URL -шаблон URL-а к странице для просмотра раздела; * IBLOCK\_TYPE\_ID - код типа инфоблоков; * IBLOCK\_CODE - символьный код инфоблока; * IBLOCK\_EXTERNAL\_ID - внешний код инфоблока.   Поля, относящиеся к элементу, для которого возвращаются разделы:   * IBLOCK\_ELEMENT\_ID - код элемента; * ADDITIONAL\_PROPERTY\_ID - код свойства (не пусто, если элемент привязан к разделу через свойство).  По умолчанию возвращаются все поля. | 12.5.7 |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php) со всеми полями для формирования url. С версии 10.0.9 в результат запроса добавлено поле IBLOCK\_ELEMENT\_ID.

### Примеры использования

```
<?
$db_old_groups = CIBlockElement::GetElementGroups($ELEMENT_ID, true);
$ar_new_groups = Array($NEW_GROUP_ID);
while($ar_group = $db_old_groups->Fetch())
	$ar_new_groups[] = $ar_group["ID"];
CIBlockElement::SetElementSection($ELEMENT_ID, $ar_new_groups);
?>Копировать
```

Новинки документации в соцсетях:
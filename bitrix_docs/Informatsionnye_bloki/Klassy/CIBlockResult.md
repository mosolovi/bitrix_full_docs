[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

CIBlockResult (доступен с 3.0.5)

CIBlockResult
=============

**CIBlockResult** - вспомогательный класс для работы с объектами результатов выборок, наследуется от класса [CDBResult](/api_help/main/reference/cdbresult/index.php) и содержит все его параметры и методы. Объекты данного класса возвращают методы [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetList](/api_help/iblock/classes/ciblockelement/getlist.php), [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetByID](/api_help/iblock/classes/ciblockelement/getbyid.php) и функции [GetIBlockElementList](/api_help/iblock/functions/getiblockelementlist.php), [GetIBlockElementListEx](/api_help/iblock/functions/getiblockelementlistex.php). Использование методов этого объекта позволяет более гибко и эффективно работать с элементами информационных блоков.

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetNext](/api_help/iblock/classes/ciblockresult/getnext.php) | Возвращает из выборки список [полей элемента](/api_help/iblock/fields.php#felement), с замененными ссылками в полях *DETAIL\_PAGE\_URL* и *LIST\_PAGE\_URL*. | 3.0.5 |
| [GetNextElement](/api_help/iblock/classes/ciblockresult/getnextelement.php) | Возвращает объект [\_CIBElement](/api_help/iblock/classes/_cibelement/index.php) элемента из выборки. | 3.1.3 |
| [SetUrlTemplates](/api_help/iblock/classes/ciblockresult/seturltemplates.php) | Устанавливает шаблоны путей для элементов. | 7.1.3 |
| [SetSectionContext](/api_help/iblock/classes/ciblockresult/setsectioncontext.php) | Метод устанавливает поля раздела в качестве родителя элемента для подстановки в шаблоны путей. | 7.1.3 |

Новинки документации в соцсетях:
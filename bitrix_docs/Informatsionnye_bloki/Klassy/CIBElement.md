[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

\_CIBElement (доступен с 3.1.3)

\_CIBElement
============

**\_CIBElement** - вспомогательный класс для работы с объектами, которые возвращает [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)::[GetNextElement](/api_help/iblock/classes/ciblockresult/getnextelement.php). Для получения различных характеристик элемента рекомендуется использовать именно этот класс, т.к. использование методов этого объекта позволяет более гибко и эффективно работать с элементами информационных блоков.

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetFields](/api_help/iblock/classes/_cibelement/getfields.php) | Возвращает массив [полей элемента](/api_help/iblock/fields.php#felement), с замененными ссылками в полях *DETAIL\_PAGE\_URL* и *LIST\_PAGE\_URL*. | 3.1.3 |
| [GetProperties](/api_help/iblock/classes/_cibelement/getproperties.php) | Возвращает все или некоторые значения свойств элемента. | 3.1.3 |
| [GetProperty](/api_help/iblock/classes/_cibelement/getproperty.php) | Возвращает значения свойства элемента. | 3.1.3 |
| [GetGroups](/api_help/iblock/classes/_cibelement/getgroups.php) | Возвращает группы, к которым привязан элемент. | 3.1.3 |

Новинки документации в соцсетях:
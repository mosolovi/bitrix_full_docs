[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

CIBlockSection (доступен с 3.0.4)

CIBlockSection
==============

**CIBlockSection** - класс для работы с разделами (группами) информационных блоков.

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetList](/api_help/iblock/classes/ciblocksection/getlist.php) | Возвращает список разделов по фильтру. | 3.0.6 |
| [GetMixedList](/api_help/iblock/classes/ciblocksection/getmixedlist.php) | Создаёт список разделов и элементов. | 5.1.0 |
| [GetByID](/api_help/iblock/classes/ciblocksection/getbyid.php) | Возвращает параметры раздела по его коду ID. | 3.0.4 |
| [Add](/api_help/iblock/classes/ciblocksection/add.php) | Добавляет в информационный блок новый раздел. | 3.0.6 |
| [Update](/api_help/iblock/classes/ciblocksection/update.php) | Изменяет параметры существующего раздела. | 3.0.6 |
| [Delete](/api_help/iblock/classes/ciblocksection/delete.php) | Удаляет раздел из информационного блока. | 3.0.4 |
| [GetCount](/api_help/iblock/classes/ciblocksection/getcount.php) | Возвращает количество подразделов. | 3.0.6 |
| [GetSectionElementsCount](/api_help/iblock/classes/ciblocksection/getsectionelementscount.php) | Возвращает количество элементов в разделе. | 3.2.1 |
| [GetTreeList](/api_help/iblock/classes/ciblocksection/gettreelist.php) | Возвращает разделы отсортированные в порядке "полностью развернутого дерева" | 3.0.4 |
| [GetNavChain](/api_help/iblock/classes/ciblocksection/getnavchain.php) | Возвращает путь от заданного раздела до корневого. | 3.0.4 |
| [ReSort](/api_help/iblock/classes/ciblocksection/resort.php) | Пересчет левой и правой границ. | 3.0.4 |
| [createMnemonicCode](/api_help/iblock/classes/ciblocksection/createmnemoniccode.php) | \* Метод создания символьного кода. | 21.300.100 |
| [generateMnemonicCode](/api_help/iblock/classes/ciblocksection/generatemnemoniccode.php) | \* Метод генерации символьного кода. | 21.300.100 |
| [isExistsMnemonicCode](/api_help/iblock/classes/ciblocksection/isexistsmnemoniccode.php) | \* Метод проверки существования символьного кода. | 21.300.100 |

\* - Методы работы с символьными кодами. Методы работают, только если в настройках инфоблока включена опция **Транслитерировать из названия при добавлении раздела** для поля Символьный код раздела.

Параметры транслитерации берутся из настроек инфоблока, но могут быть переопределены в момент использования. Исключение - опция **Использовать внешний сервис для перевода**. В этом случае методы не работают, возвращают *null*.

Язык, с которого осуществляется транслитерация, выбирается из настроек сайта, к которому привязан инфоблок. Может быть переопределен в момент использования. Если сайты, к которым привязан инфоблок, имеют различные языки, то язык транслитерации ОБЯЗАТЕЛЬНО необходимо указать при вызове методов.

Новинки документации в соцсетях:
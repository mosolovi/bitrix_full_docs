[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

CIBlockElement (доступен с 3.0.5)

CIBlockElement
==============

**CIBlockElement** - класс для работы с элементами информационных блоков.

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetList](/api_help/iblock/classes/ciblockelement/getlist.php) | Возвращает список элементов по фильтру. | 3.0.8 |
| [GetByID](/api_help/iblock/classes/ciblockelement/getbyid.php) | Возвращает элемент по его ID. | 3.0.8 |
| [GetElementGroups](/api_help/iblock/classes/ciblockelement/getelementgroups.php) | Возвращает группы, которым принадлежит элемент, по его коду. | 3.1.3 |
| [GetIBlockByID](/api_help/iblock/classes/ciblockelement/getiblockbyid.php) | Метод возвращает инфоблок по *ID* его элемента. | 3.1.3 |
| [GetProperty](/api_help/iblock/classes/ciblockelement/getproperty.php) | Получение свойств злемента. | 3.0.8 |
| [Add](/api_help/iblock/classes/ciblockelement/add.php) | Добавляет новый элемент. | 3.0.8 |
| [Update](/api_help/iblock/classes/ciblockelement/update.php) | Изменяет элемент. | 3.0.8 |
| [Delete](/api_help/iblock/classes/ciblockelement/delete.php) | Удаляет элемент из информационного блока. | 3.0.5 |
| [SetElementSection](/api_help/iblock/classes/ciblockelement/setelementsection.php) | Привязывает элемент информационного блока к группам. | 3.1.3 |
| [SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php) | Сохраняет свойства элемента информационного блока. | 3.0.5 |
| [SetPropertyValuesEx](/api_help/iblock/classes/ciblockelement/setpropertyvaluesex.php) | Сохраняет значения всех свойств элемента информационного блока. В отличие от [SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php) может не содержать полный набор значений. | 6.0.0 |
| [SetPropertyValueCode](/api_help/iblock/classes/ciblockelement/setpropertyvaluecode.php) | Изменяет значение свойства элемента. | 3.0.13 |
| [UpdateSearch](/api_help/iblock/classes/ciblockelement/updatesearch.php) | Индексирует указанный элемент в модуле поиска. | 3.0.8 |
| [CounterInc](/api_help/iblock/classes/ciblockelement/counterinc.php) | Увеличивает счетчик показов элемента. | 3.3.8 |
| [SubQuery](/api_help/iblock/classes/ciblockelement/SubQuery.php) | Позволяет использовать подзапросы. | 10.0.2 |
| [GetPropertyValues](/api_help/iblock/classes/ciblockelement/getpropertyvalues.php) | Метод позволяет получить значения свойств для элементов одного информационного блока, отобранных по фильтру | 14.0.0 |
| [GetPropertyValuesArray](/api_help/iblock/classes/ciblockelement/getpropertyvaluesarray.php) | Получение значений свойств элементов одного инфоблока для компонента. | 14.5.0 |
| [createMnemonicCode](/api_help/iblock/classes/ciblockelement/createmnemoniccode.php) | \* Метод создания символьного кода. | 21.300.100 |
| [generateMnemonicCode](/api_help/iblock/classes/ciblockelement/generatemnemoniccode.php) | \* Метод генерации символьного кода. | 21.300.100 |
| [isExistsMnemonicCode](/api_help/iblock/classes/ciblockelement/isexistsmnemoniccode.php) | \* Метод проверки существования символьного кода. | 21.300.100 |
| [getPublicElementsOrmFilter](/api_help/iblock/classes/ciblockelement/getpublicelementsormfilter.php) | \* Метод для дополнения фильтра orm на основе массива. | 21.300.100 |

\* - Методы работы с символьными кодами. Они работают, только если в настройках инфоблока включена опция **Транслитерировать из названия при добавлении элемента** для поля Символьный код элемента.

Параметры транслитерации берутся из настроек инфоблока, но могут быть переопределены в момент использования. Исключение - опция **Использовать внешний сервис для перевода**. В этом случае методы не работают, возвращают *null*.

Язык, с которого осуществляется транслитерация, выбирается из настроек сайта, к которому привязан инфоблок. Может быть переопределен в момент использования. Если сайты, к которым привязан инфоблок, имеют различные языки, то язык транслитерации ОБЯЗАТЕЛЬНО необходимо указать при вызове методов.

Новинки документации в соцсетях:
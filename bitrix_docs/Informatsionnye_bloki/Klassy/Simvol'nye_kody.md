[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Символьные коды](/api_help/iblock/classes/mnemoniccode/index.php)

Методы для проверки и генерации символьных кодов (с версии 21.300.100)

Методы для проверки и генерации символьных кодов
================================================

Перечень методов, их параметры вызова и тип возвращаемого результата идентичны для классов [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php) и [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php).

Методы работают, только если в настройках инфоблока включена опция **Транслитерировать из названия при добавлении элемента** для поля Символьный код (класс *CIBlockElement*) и **Транслитерировать из названия при добавлении раздела** для поля Символьный код раздела (класс *CIBlockSection*)

Параметры транслитерации берутся из настроек инфоблока, но могут быть переопределены в момент использования. Исключение - опция **Использовать внешний сервис для перевода**. В этом случае методы не работают, возвращают *null*.

Язык, с которого осуществляется транслитерация, выбирается из настроек сайта, к которому привязан инфоблок. Может быть переопределен в момент использования. Если сайты, к которым привязан инфоблок, имеют различные языки, то язык транслитерации ОБЯЗАТЕЛЬНО необходимо указать при вызове методов.

Новинки документации в соцсетях:
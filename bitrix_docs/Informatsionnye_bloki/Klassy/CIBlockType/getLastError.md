[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockType](/api_help/iblock/classes/ciblocktype/index.php)

getLastError (24.100.0)

getLastError
============

```
string
CIBlockType::getLastError()Копировать
```

Метод получает текст ошибок, если вызов методов [Add](/api_help/iblock/classes/ciblocktype/add.php), [Update](/api_help/iblock/classes/ciblocktype/update.php), CheckFields завершился неудачей. Метод нестатический.

  

**Примечание**. Метод получает ошибки из свойства `LAST_ERROR`. Прямое обращение к свойству `LAST_ERROR` не рекомендуется с версии 24.100.0.

  

#### Параметры метода

Без параметров

  

#### Возвращаемое значение

Метод возвращает строку с текстом ошибок или пустую строку, если ошибок нет.

Новинки документации в соцсетях:
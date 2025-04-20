[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

Пользовательские свойства (доступны с 5.1.0)

Пользовательские свойства
=========================

Пользовательские свойства модуля информационных блоков позволяют изменять представление (формы ввода и т.п.) стандартных свойств расширяя их возможности. Фактически такое свойство представляет собой набор обработчиков событий вызываемых при построении административного интерфейса, публичной части сайта или API функций.

При первом обращении к методам пользовательских свойств вызываются обработчики события [OnIBlockPropertyBuildList](/api_help/iblock/events/OnIBlockPropertyBuildList.php). Строится список свойств и при необходимости вызываются их методы.

Примеры конкретной реализации свойств можно посмотреть в файлах модуля информационных блоков **classes/general/prop\_\*.php**

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetUserTypeDescription](/api_help/iblock/classes/user_properties/GetUserTypeDescription.php) | Описание свойства | 5.0.1 |
| [CheckFields](/api_help/iblock/classes/user_properties/CheckFields.php) | Проверка правильности значения | 5.0.1 |
| [GetLength](/api_help/iblock/classes/user_properties/GetLength.php) | Проверка длинны значения | 7.1.0 |
| [ConvertToDB](/api_help/iblock/classes/user_properties/ConvertToDB.php) | Сохранение в БД | 5.0.1 |
| [ConvertFromDB](/api_help/iblock/classes/user_properties/ConvertFromDB.php) | Извлечение из БД | 5.0.1 |
| [GetPropertyFieldHtml](/api_help/iblock/classes/user_properties/GetPropertyFieldHtml.php) | Отображение в форме редактирования | 5.0.1 |
| [GetAdminListViewHTML](/api_help/iblock/classes/user_properties/GetAdminListViewHTML.php) | Показ в списке | 6.0.3 |
| [GetPublicViewHTML](/api_help/iblock/classes/user_properties/GetPublicViewHTML.php) | Отображение в публичной части | 6.5.2 |
| [GetPublicEditHTML](/api_help/iblock/classes/user_properties/GetPublicEditHTML.php) | Редактирование в публичной части | 7.1.4 |
| [GetSearchContent](/api_help/iblock/classes/user_properties/GetSearchContent.php) | Индексация значений | 8.6.1 |
| [PrepareSettings](/api_help/iblock/classes/user_properties/PrepareSettings.php) | Сохранение настроек | 8.6.1 |
| [GetSettingsHTML](/api_help/iblock/classes/user_properties/GetSettingsHTML.php) | Редактирование настроек | 8.6.1 |
| [GetPropertyFieldHtmlMulty](/api_help/iblock/classes/user_properties/getpropertyfieldhtmlmulty.php) | Вывод формы редактирования множественного свойства. Если отсутствует, то используется [GetPropertyFieldHtml](/api_help/iblock/classes/user_properties/GetPropertyFieldHtml.php) для каждого значения отдельно (у множественных свойств). | 5.0.1 |
| [GetAdminFilterHTML](/api_help/iblock/classes/user_properties/getadminfilterhtml.php) | Выводит html для фильтра по свойству на административной странице списка элементов инфоблока. | 7.0.1 |
| [GetPublicFilterHTML](/api_help/iblock/classes/user_properties/getpublicfilterhtml.php) | Выводит html для фильтра по свойству на публичной странице списка элементов инфоблока. | 8.0.1 |

#### Фильтрация

Для работы фильтра необходимо в *GetUserTypeDescription* добавить строчку вида:

```
"AddFilterFields" => array(__CLASS__,'AddFilterFields'),Копировать
```

и в классе объявить метод:

```
public static function AddFilterFields($arProperty, $control, &$arFilter, &$filtered) Копировать
```

Надо учитывать что этот метод не обязательный. Метод нужен только если фильтр сильно "не стандартный".

Новинки документации в соцсетях:
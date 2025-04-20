[Информационные блоки](/api_help/iblock/index.php)

Для разработчиков

Для разработчиков
=================

Включить вкладки

Описание

Публичные функции и возвращаемые значения

Классы модуля информационных блоков

Компоненты 2.0

### Описание

Модуль **Информационные блоки** - мощный и в то же время гибкий механизм для хранения и выборки информации различными способами. API модуля состоит из нескольких высокоуровневых функций для выборки данных в публичном разделе сайта и набора классов с низкоуровневыми методами для более специализированной работы.

Перед использованием модуля необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<?
if(CModule::IncludeModule("iblock"))
{ 
	//здесь можно использовать функции и классы модуля
} 
?>Копировать
```

Для получения данных при показе в публичном разделе сайта можно пользоваться функциями с простыми параметрами и предустановленными фильтрами. Эти функции выбирают по умолчанию те значения, которые подходят для места выборки, а именно только активные, привязанные к текущему сайту, подходящие по правам доступа и т.п.

Вся работа с **датами** через API (вставка, выборка, фильтры и т.п.) производится в **формате текущего сайта** или, если в административной части, в формате текущего языка.

### Публичные функции и возвращаемые значения

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetIBlockList](/api_help/iblock/functions/getiblocklist.php) | Возвращает список информационных блоков по фильтру. | 3.0.5 |
| [GetIBlock](/api_help/iblock/functions/getiblock.php) | Возвращает информационный блок по заданному коду. | 3.0.5 |
| [GetIBlockElementListEx](/api_help/iblock/functions/getiblockelementlistex.php) | Возвращает список элементов по фильтру. | 3.0.5 |
| [GetIBlockElementList](/api_help/iblock/functions/getiblockelementlist.php) | Возвращает список элементов из определённого информационного блока. | 3.0.5 |
| [GetIBlockElement](/api_help/iblock/functions/getiblockelement.php) | Возвращает элемент по заданному коду. | 3.0.5 |
| [GetIBlockSectionList](/api_help/iblock/functions/getiblocksectionlist.php) | Возвращает список папок из определённого информационного блока. | 3.0.5 |
| [GetIBlockSection](/api_help/iblock/functions/getiblocksection.php) | Возвращает раздел по заданному коду. | 3.0.5 |

Если ваша задача более специфична и публичных функций недостаточно, или необходимо не только выбрать, но и изменить данные, то необходимо воспользоваться набором классов для работы с объектами модуля информационных блоков.

### Классы модуля информационных блоков

| Класс | Описание | С версии |
| --- | --- | --- |
| [CIBlock](/api_help/iblock/classes/ciblock/index.php) | Класс для работы с информационными блоками. | 3.0.3 |
| [CIBlockCMLExport](/api_help/iblock/classes/ciblockcmlexport/index.php) | Класс для экспорта данных инфоблока в xml-формате. | 6.5.0 |
| [CIBlockCMLImport](/api_help/iblock/classes/ciblockcmlimport/index.php) | Класс для импорта данных инфоблока в xml-формате. | 6.5.0 |
| [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php) | Класс для работы с элементами информационных блоков. | 3.0.5 |
| [CIBlockFormatProperties](/api_help/iblock/classes/ciblockformatproperties/dateformat.php) |  | 5.9.0 |
| [CIBlockPriceTools](/api_help/iblock/classes/ciblockpricetools/canbuy.php) |  | 5.9.0 |
| [CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php) | класс для работы со свойствами информационных блоков. | 3.0.3 |
| [CIBlockPropertyEnum](/api_help/iblock/classes/ciblockpropertyenum/index.php) | Класс для работы с вариантами значений для свойств типа "список". | 3.1.3 |
| [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php) | Вспомогательный класс для работы с объектами результатов выборок. | 3.0.5 |
| [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php) | Класс для работы с RSS лентами. | 3.0.14 |
| [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php) | Класс для работы с группами информационных блоков. | 3.0.4 |
| [CIBlockType](/api_help/iblock/classes/ciblocktype/index.php) | Класс для работы с типами информационных блоков. | 3.1.3 |
| [CIBlockXMLFile](/api_help/iblock/classes/ciblockxmlfile/index.php) | Класс для работы с файлами XML. | 6.5.0 |
| [Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php) | Позволяют изменять представление (формы ввода и т.п.) стандартных свойств расширяя их возможности. | 5.1.0 |
| [\_CIBElement](/api_help/iblock/classes/_cibelement/index.php) | Вспомогательный класс для работы с объектом выборки элемента. | 3.1.3 |

### Компоненты 2.0

Модуль включает в себя следующие Компоненты 2.0:
  

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| **Новости** | | |
| [Новости (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/content/articles_and_news/news.php) | **news** | Позволяет создать новостной раздел на сайте. |
| [Календарь](https://dev.1c-bitrix.ru/user_help/components/content/articles_and_news/news_calendar.php) | **news.calendar** | Служит для формирования и вывода календаря новостей или событий. |
| [Новость детально](https://dev.1c-bitrix.ru/user_help/components/content/articles_and_news/news_detail.php) | **news.detail** | Осуществляет вывод детального описания новости. |
| [Все новости](https://dev.1c-bitrix.ru/user_help/components/content/articles_and_news/news_index.php) | **news.index** | Выводит новости из различных инфоблоков. |
| [Лента](https://dev.1c-bitrix.ru/user_help/components/content/articles_and_news/news_line.php) | **news.line** | Осуществляет вывод списка элементов инфоблоков с датой и заголовком со ссылкой на страницу с подробной информацией. |
| [Список новостей](https://dev.1c-bitrix.ru/user_help/components/content/articles_and_news/news_list.php) | **news.list** | Выводит список новостей из одного информационного блока. |
| **Фотогалерея** | | |
| [Фотогалерея (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery/photo.php) | **photo** | Позволяет получить полнофункциональную фотогалерею, создавая физически только одну страницу. |
| [Фотография детально](https://dev.1c-bitrix.ru/user_help/components/content/photogallery/photo_detail.php) | **photo.detail** | Выводит детальную информацию по фотографии. |
| [Случайное фото](https://dev.1c-bitrix.ru/user_help/components/content/photogallery/photo_random.php) | **photo.random** | Служит для показа одной произвольной фотографии. |
| [Фотографии раздела](https://dev.1c-bitrix.ru/user_help/components/content/photogallery/photo_section.php) | **photo.section** | Выводит все фотографии из выбранного раздела. |
| [Разделы с TOP'ом фотографий](https://dev.1c-bitrix.ru/user_help/components/content/photogallery/photo_sections_top.php) | **photo.sections.top** | Служит для вывода TOP'а фотографий, сгруппированных по разделам. |
| **Фотогалерея 2.0** | | |
| [Фотогалерея 2.0 (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery.php) | **photogallery** | Позволяет получить полнофункциональную фотогалерею, создавая физически только одну страницу. |
| [Фото](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_detail.php) | **photogallery.detail** | Выводит детальную информацию по фотографии. |
| [Фото (комментарии)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_detail_comment.php) | **photogallery.detail.comment** | Служит для создания комментариев к фотографии. |
| [Фото (редактирование)](http://dev.1c-bitrix.ru/user_help/service/photogallery/components_2/photogallery_detail_edit.php) | **photogallery.detail.edit** | Служит для редактирования свойств фотографии. |
| [Фото (список)](http://dev.1c-bitrix.ru/user_help/service/photogallery/components_2/photogallery_detail_list.php) | **photogallery.detail.list** | Выводит список фотографий. |
| [Список фото со слайдером](https://dev.1c-bitrix.ru/user_help/service/photogallery/components_2/photogallery_detail_list_ex.php") | **photogallery.detail.list.ex** | Выводит список фотографий во всплывающем окне со слайдером и комментариями. |
| [Фотогалерея (редактирование)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_detail_edit.php) | **photogallery.gallery.edit** | Выводит форму редактирования параметров фотогалереи пользователя. |
| [Фотогалерея (список)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_gallery_list.php) | **photogallery.gallery.list** | Выводит список фотогалерей пользователя. |
| [Фотогалерея (шаблоны)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_interface.php) | **photogallery.interface** | Подключает библиотеку вспомогательных шаблонов. Компонент ничего не выводит. |
| [Flash-слайдшоу](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_imagerotator.php) (Не поддерживается с версии 15.0.0) | **photogallery.imagerotator** | Циклически проигрывает фотографии из фотогалереи. |
| [Альбом](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_section.php) | **photogallery.section** | Выводит полную информацию об одном альбоме. |
| [Альбом (редактирование)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_section_edit.php) | **photogallery.section.edit** | Позволяет отредактировать данные альбома: изменить название, дату создания, ввести описание, ограничить доступ к альбому по паролю. |
| [Альбом (редактирование обложки)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_section_edit_icon.php) | **photogallery.section.edit.icon** | Служит для редактирования обложки альбома. |
| [Альбом (список)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_section_list.php) | **photogallery.section.list** | Выводит список альбомов с информацией о количестве фотографий, вложенных альбомов в каждом и ссылками на просмотр содержимого альбомов. |
| [Фото (загрузка)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_upload.php) | **photogallery.upload** | Служит для загрузки фотографии. |
| [Панель](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_user.php) | **photogallery.user** | Выводит информацию о галерее пользователя. |
| [Фотогалерея 2.0 (многопользовательская) (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/content/photogallery2/photogallery_user_composite.php) | **photogallery\_user** | Позволяет получить полнофункциональную многопользовательскую фотогалерею, создавая физически только одну страницу. |
| **Каталог** | | |
| [Каталог (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog.php) | **catalog** | Осуществляет вывод полного каталога товаров из определенного инфоблока. |
| [Список сравниваемых элементов каталога](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_compare_list.php) | **catalog.compare.list** | Выводит список сравниваемых элементов каталога в виде небольшой таблицы. |
| [Таблица сравнения](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_compare_result.php) | **catalog.compare.result** | Выводит таблицу сравниваемых элементов каталога. |
| [Элемент каталога детально](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_element.php) | **catalog.element** | Выводит детальную информацию по элементу каталога. |
| [Фильтр по элементам](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_filter.php) | **catalog.filter** | Выводит форму фильтра для фильтрации элементов информационых блоков. |
| [Список связанных элементов](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_link_list.php) | **catalog.link.list** | Выводит список элементов, связанных с заданным. |
| [Список информационных блоков заданного типа](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_main.php) | **catalog.main** | Выводит список всех информационных блоков заданного типа. |
| [Элементы раздела](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_section.php) | **catalog.section** | Выводит список элементов раздела с указанным набором свойств. |
| [Структура разделов](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_section_list.php) | **catalog.section.list** | Выводит список разделов инфоблока с указанным количеством элементов в каждом разделе. |
| [Разделы с top'ом элементов](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_sections_top.php) | **catalog.sections.top** | Выводит Top элементов сгруппированных по разделам; элементы выводятся в таблице. |
| [Top элементов каталога](https://dev.1c-bitrix.ru/user_help/components/content/catalog/catalog_top.php) | **catalog.top** | Выводит в таблице Top элементов из всех разделов в соответствии с заданной сортировкой (используется как правило на главной странице сайта). |
| **RSS** | | |
| [RSS новости (экспорт)](https://dev.1c-bitrix.ru/user_help/components/content/rss/rss_out.php) | **rss.out** | Предназначен для создания страницы, которая отдает выбранные новости вашего сайта в формате RSS. |
| [RSS новости (импорт)](https://dev.1c-bitrix.ru/user_help/components/content/rss/rss_show.php) | **rss.show** | Предназначен для импорта новостей с другого сайта. |
| **Добавление элементов** | | |
| [Добавление элементов инфоблока (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/content/adding/iblock_element_add.php) | **iblock.element.add** | Осуществляет вывод списка элементов указанного инфоблока, добавление/редактирование элементов и их удаление в зависимости от прав пользователя. |
| [Форма добавления / редактирования](https://dev.1c-bitrix.ru/user_help/components/content/adding/iblock_element_add_form.php) | **iblock.element.add.form** | Осуществляет вывод формы создания (редактирования) элемента указанного информационного блока. |
| [Список своих элементов](https://dev.1c-bitrix.ru/user_help/components/content/adding/iblock_element_add_list.php) | **iblock.element.add.list** | Осуществляет вывод списка доступных пользователю элементов указанного инфоблока, ссылок **Добавить**, **Редактировать**, **Удалить**. |
| **Инфоблоки** | | |
| [Голосование](https://dev.1c-bitrix.ru/user_help/components/content/infoblocks/iblock_vote.php) | **iblock.vote** | Реализует возможность голосования для пользователей. |
| **Универсальные списки** | | |
| [Универсальные списки](https://dev.1c-bitrix.ru/user_help/components/content/lists/lists.php) | **lists** | Позволяет вести полнофункциональную работу с универсальными списками, создавая физически только одну страницу. |
| [Списки](https://dev.1c-bitrix.ru/user_help/components/content/lists/lists_lists.php) | **lists.lists** | Выводит таблицу универсальных списков, доступных для просмотра и изменения. |
| [Список](https://dev.1c-bitrix.ru/user_help/components/content/lists/lists_list.php) | **lists.list** | Выводит разделы и элементы универсального списка с возможностью навигации и редактирования. |
| [Разделы списка](https://dev.1c-bitrix.ru/user_help/components/content/lists/lists_sections.php) | **lists.sections** | Позволяет удалить и изменить разделы универсального списка. |
| [Редактирование элемента](https://dev.1c-bitrix.ru/user_help/components/content/lists/lists_element_edit.php) | **lists.element.edit** | Выводит форму редактирования элемента списка. |
| [Настройки списка](https://dev.1c-bitrix.ru/user_help/components/content/lists/lists_list_edit.php) | **lists.list.edit** | Показывает форму настроек универсального списка. |
| [Поля списка](https://dev.1c-bitrix.ru/user_help/components/content/lists/lists_fields.php) | **lists.fields** | Показывает поля универсального списка и позволяет их редактировать. |
| [Настройки поля списка](https://dev.1c-bitrix.ru/user_help/components/content/lists/lists_field_edit.php) | **lists.field.edit** | Показывает форму настройки поля универсального списка. |
| [Навигационная цепочка](https://dev.1c-bitrix.ru/user_help/components/content/lists/lists_element_navchain.php) | **lists.element.navchain** | Добавляет к выводу обычного компонента **Навигационная цепочка (bitrix:breadcrumb)** элемент списка. |

Новинки документации в соцсетях:
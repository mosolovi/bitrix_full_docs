[Поиск](/api_help/search/index.php)

Для разработчиков

Для разработчиков
=================

Включить вкладки

Описание

Публичные функции и возвращаемые значения

Классы модуля поиска

События модуля поиска

Компоненты 2.0

### Описание

Перед использованием модуля **Поиск** необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<?
if(CModule::IncludeModule("search"))
{
	//здесь можно использовать функции модуля
}
?>
Копировать
```

Работа модуля поиска сводится к предварительному индексированию и последующей выдаче информации сайте по запросу пользователя. Индексирование заключается в сохранении времени изменения, модуля-владельца, кода элемента, языка, web-адреса, заголовка, текста и двух произвольных параметров индексируемого элемента, а так же списка кодов групп пользователей, которые имеют доступ на чтение (как минимум) к данному элементу. Поиск заключается в выдаче списка результатов, удовлетворяющих введенной строке запроса (обрабатывается с учётом языка запросов), а так же набору установленных ограничений (модуль-владелец, код элемента, сайт, два произвольных параметра).

Алгоритм работы модуля поиска таков, что он не имеет никакой информации по характеру и структуре данных других модулей. При индексации модули по запросу сами отдают модулю поиска ту информацию, которую необходимо проиндексировать. Передача осуществляется в виде массива заданной структуры. Связь между модулем поиска и другими модулями системы осуществляется через систему сообщений.

#### Смотрите также:

* Специальные [константы](/api_help/search/constants.php).

### Публичные [функции](/api_help/search/functions/index.php) и возвращаемые значения

| Функция | Описание | С версии |
| --- | --- | --- |
| [stemming](/api_help/search/functions/stemming.php) | Возвращает массив неизменных основ слов. | 6.5.0 |
| [stemming\_default](/api_help/search/functions/stemming_default.php) | Функция морфологического анализа текста применяемая по умолчанию. | 6.5.0 |
| [stemming\_stop\_default](/api_help/search/functions/stemming_stop_default.php) | Функция определения стоп слова применяемая по умолчанию. | 6.5.0 |
| [stemming\_letter\_default](/api_help/search/functions/stemming_letter_default.php) | Функция возвращает алфавит по умолчанию. | 6.5.0 |
| [tags\_prepare](/api_help/search/functions/tags_prepare.php) | Возвращает массив тегов. | 6.5.0 |
| [InputTags](/api_help/search/functions/inputtags.php) | Возвращает код html для ввода тегов с поддержкой автодополнения. | 6.5.0 |

### [Классы](/api_help/search/classes/index.php) модуля поиска

| Класс | Описание | С версии |
| --- | --- | --- |
| [CSearch](/api_help/search/classes/csearch/index.php) | Класс для индексирования сайта и осуществления поиска по индексу. | 3.0.1 |
| [CSearchCustomRank](/api_help/search/classes/csearchcustomrank/fields.php) | Класс поддержки правил сортировки. | 4.1.2 |
| [CSiteMap](/api_help/search/classes/csitemap/index.php) | Класс поддержки Google Sitemap. | 4.0.12 |
| [CSearchTags](/api_help/search/classes/csearchtags/index.php) | Класс поддержки тегов. | 6.5.0 |

### [События модуля](/api_help/search/events/index.php) поиска

| Событие | Описание | С версии |
| --- | --- | --- |
| [BeforeIndex](/api_help/search/events/beforeindex.php) | Вызывается перед индексацией элемента. | 5.1.0 |
| [OnSearch](/api_help/search/events/onsearch.php) | Вызывается перед выполнением поисковых запросов. | 3.0.4 |
| [OnReIndex](/api_help/search/events/onreindex.php) | Вызывается при построении поискового индекса. | 3.0.4 |
| [OnSearchGetFileContent](/api_help/search/events/onsearchgetfilecontent.php) | Вызывается по время переиндексации данных главного модуля. | 6.5.6 |
| [OnSearchGetURL](/api_help/search/events/onsearchgeturl.php) | Вызывается при форматировании элемента в результатах поиска. | 4.0.0 |
| [OnSearchGetTag](/api_help/search/events/onsearchgettag.php) | Вызывается при разборе строки тегов. | 7.1.2 |
| [OnBeforeFullReindexClear](/api_help/search/events/onbeforefullreindexclear.php) | Вызывается в начале первого шага полной переиндексации, непосредственно перед удалением всех данных поискового индекса. | 8.0.4 |
| [OnBeforeIndexDelete](/api_help/search/events/onbeforeindexdelete.php) | Вызывается перед удалением части поискового индекса. | 8.0.4 |
| [OnBeforeIndexUpdate](/api_help/search/events/onbeforeindexupdate.php) | Вызывается перед обновлением поискового индекса. | 8.0.4 |
| [OnAfterIndexAdd](/api_help/search/events/onafterindexadd.php) | Вызывается после добавления новых данных в поисковый индекс. | 8.0.4 |
| [OnSearchCheckPermissions](/api_help/search/events/onsearchcheckpermissions.php) | Вызывается при построении поискового запроса. | 8.0.4 |

### Компоненты 2.0

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Форма поиска](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/search/search_form.php) | **search.form** | Служит для вывода формы поиска. |
| [Стандартная страница поиска](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/search/search_page.php) | **search.page** | Служит для создания страницы поиска. |
| [Облако тегов](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/search/search_tags_cloud.php) | **search.tags.cloud** | Предназначен для вывода облака тегов. |
| [Форма ввода тегов](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/search/search_tags_input.php) | **search.tags.input** | Предназначен для вывода формы ввода тегов. |
| [Поиск по заголовкам](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/search/search_title.php) | **search.title** | Предназначен для вывода поля поиска по заголовкам. |
| [Поле ввода поискового запроса](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/search/search_suggest_input.php) | **search.suggest.input** | Cлужит для вывода поля ввода поискового запроса с подсказкой. |

Новинки документации в соцсетях:
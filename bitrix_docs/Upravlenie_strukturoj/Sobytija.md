[Управление структурой](/api_help/fileman/index.php)

[События](/api_help/fileman/events/index.php)

Список событий

Список событий
==============

Включить вкладки

Описание и события

Смотрите также

### Описание и события

Ниже представлен список событий модуля "Управления структурой". Для регистрации обработчика укажите в качестве идентификатора модуля - "fileman".

#### События, связанные с визуальным HTML-редактором

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnBeforeHTMLEditorScriptsGet](/api_help/fileman/events/onbeforehtmleditorscriptsget.php) | непосредственно перед подключением JavaScript-файлов редактора. Позволяет добавить в список подключаемых файлов дополнительный JavaScript файл или файл стилей. | CFileMan::ShowHTMLEditControl | 6.5.6 |
| OnBeforeLightEditorScriptsGet | перед подключением JavaScript-файлов упрощенного редактора. | CLightHTMLEditor::Init | 8.5.3 |
| [OnIncludeHTMLEditorScript](/api_help/fileman/events/onincludehtmleditorscript.php) | непосредственно после подключения редактора, на странице вызова, но до его инициализации. | CFileMan::ShowHTMLEditControl | 5.0.2 |
| OnIncludeLightEditorScript | непосредственно после подключения упрощенного редактора, на странице вызова, но до его инициализации. | CLightHTMLEditor::InitScripts | 9.5.3 |
| OnIframeBeforeGetValue | Событие позволяет модифицировать содержимое получаемое из визредактора. |  | 17.5.1 |

#### Прочие события



| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| OnMedialibItemView | происходит перед созданием и выдачей элемента медиабиблиотеки в виде HTML для показа пользователю. | CMedialib::GetItemViewHTML | 9.0.0 |

### Смотрите также

* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Взаимодействие модулей](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=2825)

Новинки документации в соцсетях:
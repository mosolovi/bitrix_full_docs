[Управление структурой](/api_help/fileman/index.php)

[События](/api_help/fileman/events/index.php)

OnBeforeHTMLEditorScriptsGet

OnBeforeHTMLEditorScriptsGet
============================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
array функция-обработчик(
	string editorName
	array arEditorParams
);Копировать
```

Событие "OnBeforeHTMLEditorScriptsGet" вызывается перед загрузкой JavaScript и CSS файлов редактора и позволяет добавить пользовательские файлы, которые будут подгружаться после файлов визуального редактора. Создание обработчика данного представляет собой простейший способ модифицировать встроенный визуальный редактор путём расширения или переопределения текущего функционала.

**Внимание**. Событие работает только в рамках старого визуального редактора.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **editorName** | Имя подключаемого редактора. |
| **arEditorParams** | Массив параметров подключаемого редактора. |

#### Структура результата

Результатом выполнения функции-обработчика должен быть ассоциативный массив,
который может содержать поля "JS" и "CSS" каждое из которых должно являться
линейным массивом имен подключаемых файлов c соответствующим расширением.

Файлы, имена которых возвращаются в качестве элементов массивов в
полях "JS" и "CSS" должны находиться в папке
*/bitrix/admin/htmleditor2*

### Смотрите также

* [Событие
  "OnIncludeHTMLEditorScript"](/api_help/fileman/events/onincludehtmleditorscript.php)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("fileman", "OnBeforeHTMLEditorScriptsGet", "addEditorScriptsHandler");
public static function addEditorScriptsHandler($editorName,$arEditorParams)
{
	// Проверяем, если подключается редактор для редактирования статических страниц
	if ($editor_name == 'filesrc')
		return array(
			"JS" => array('my_scripts.js'),
			"CSS" => array('my_styles.css')
		);
		
	return array();
}
?>
<?
// файл /bitrix/admin/htmleditor2/my_scripts.js
// Переопределяем стандартную панель инструментов, удаляя из нее кнопки "Настройки", "Выделить все" и "Проверка орфографии"
arToolbars['standart'] = [
	BX_MESS.TBSStandart,
		[
		arButtons['Fullscreen'], 'separator',
		arButtons['Cut'], arButtons['Copy'], arButtons['Paste'], arButtons['pasteword'], arButtons['pastetext'], arButtons['separator'],
		arButtons['Undo'], arButtons['Redo'], arButtons['separator'],
		arButtons['borders'], 'separator',
		arButtons['table'], arButtons['anchor'], arButtons['CreateLink'], arButtons['deletelink'], arButtons['image'], 'separator',
		arButtons['SpecialChar'], arButtons['spellcheck']
		]
	];
?>
/* файл /bitrix/admin/htmleditor2/my_styles.css
переопределяем цвет фона редактора (только для Mozilla Firefox) */
.bxedmainframe IFRAME{
	background-color: #CCCCCC;
}Копировать
```

Новинки документации в соцсетях:
[JS библиотека](/api_help/js_lib/index.php)

Регистрация своих расширений

Регистрация своих расширений
============================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CJSCore::RegisterExt(
	"my_extension", 
	array(
		"js" => "/path/to/js/my_ext.js",
		"css" => "/path/to/css/my_ext.css",
		"lang" => "/path/to/lang/".LANGUAGE_ID. "/lang.php",
		"rel" => Array("ajax", "popup", "ls"),
		"skip_core" => false | true,
	)
);Копировать
```

Функция регистрирует собственные расширения.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| my\_extension | имя расширения |
| Array | Массив параметров расширения:  * **js** - Путь до файла расширения; * **css** - Путь до файла css расширения; * **lang** - Путь до языкового файла расширения; * **rel** - Список "зависимостей". При подключении собственного расширения зависимости будут подключены автоматически. * **skip\_core** - При подключении расширения не требуется подключение **core.js**. |

### Примеры использования

```
<?
require($_SERVER["DOCUMENT_ROOT"]."/bitrix/header.php");
$APPLICATION->SetTitle("Свои расширения");
	CJSCore::RegisterExt("db_js_demo", Array(
		"js" =>    "/script_demo.js",
		"lang" =>   "/lang_js.php",
		"rel" =>   array('jquery')
	));
	CJSCore::Init(array("db_js_demo"));
?>
<div id="hideBlock" style="display:none;">
	<h1>Hello</h1>
	<p>text</p>
</div>
<script>
	window.BXDEBUG = true;
BX.ready(function(){
	BX.PREFIXName('HELLO');
	//BX.PREFIXName.testJQ('#demo');
});
</script>
<p id="demo">click Me</p>
<?require($_SERVER["DOCUMENT_ROOT"]."/bitrix/footer.php");?>Копировать
```

Новинки документации в соцсетях:
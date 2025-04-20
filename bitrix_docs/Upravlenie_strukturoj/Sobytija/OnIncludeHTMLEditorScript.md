[Управление структурой](/api_help/fileman/index.php)

[События](/api_help/fileman/events/index.php)

OnIncludeHTMLEditorScript

OnIncludeHTMLEditorScript
=========================

```
функция-обработчик();Копировать
```

Событие "OnIncludeHTMLEditorScript" вызывается после подключения файлов визуального редактора.
Может использоваться в тех случаях, когда для модификации редактора недостаточно стандартного подключения внешних JavaScript файлов ([Событие "OnBeforeHTMLEditorScriptsGet"](/api_help/fileman/events/onbeforehtmleditorscriptsget.php)).

**Внимание**. Событие работает только в рамках старого визуального редактора.

#### Смотрите также

* [Событие "OnBeforeHTMLEditorScriptsGet"](/api_help/fileman/events/onbeforehtmleditorscriptsget.php)

#### Пример функции-обработчика:

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("fileman", "OnIncludeHTMLEditorScript", "OnIncludeHTMLEditorHandler");
public static function OnIncludeHTMLEditorHandler()
{
	?>
	<script>
	//Переопределение функции установки полноэкранного режима редактора
	BXHTMLEditor.prototype.SetFullscreen_ = BXHTMLEditor.prototype.SetFullscreen;
	BXHTMLEditor.prototype.SetFullscreen = function (bFull)
	{
		alert('My alert!');
		this.SetFullscreen_(bFull);
	}
	</script>
	<?
}
?>Копировать
```

Новинки документации в соцсетях:
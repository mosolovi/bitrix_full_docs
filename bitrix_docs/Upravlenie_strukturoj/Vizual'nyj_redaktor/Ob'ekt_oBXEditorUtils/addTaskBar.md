[Управление структурой](/api_help/fileman/index.php)

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

addTaskBar

addTaskBar
==========

Включить вкладки

Описание и параметры

Пример добавления панели задач в редактор

### Описание и параметры

Используется для добавления пользовательской панели задач в визуальный редактор.  
Требует предварительного объявления класса пользовательской панели задач.(см. [Добавление панелей задач](/api_help/fileman/editor/add_taskbar.php))

```
void
oBXEditorUtils.addTaskBar(
	string className,
	int taskbarSetPos,
	string taskbarTitle,
	array params
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *className* | Имя класса панели задач. |
| *taskbarSetPos* | Параметр, определяющий положение панели задач, относительно области редактирования:  |  |  | | --- | --- | | **0** | Вверху, над областью редактирования | | **1** | Слева от области редактирования | | **2** | Справа от области редактирования | | **3** | Внизу, под областью редактирования | |
| *taskbarTitle* | Название панели задач, отображается в заголовке. |
| *params* | Дополнительные параметры |

### Пример добавления панели задач в редактор

```
<script>
function CustomTaskbar()
{
	var oTaskbar = this;
	
	CustomTaskbar.prototype.OnTaskbarCreate = function ()
	{
		//...
	}
	
	CustomTaskbar.prototype.UnParseElement = function(node)
	{
		//...
	}
	
	CustomTaskbar.prototype.OnElementDragEnd = function(oEl)
	{
		//...
	}
}
//Добавление панели задач
oBXEditorUtils.addTaskBar('CustomTaskbar',2,"Help",[]);
</script>Копировать
```

Новинки документации в соцсетях:
[Управление структурой](/api_help/fileman/index.php)

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

getCustomNodeParams

getCustomNodeParams
===================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

Возвращает параметры "искусственного" элемента\* в виде массива, заменяющего некоторый фрагмент кода в документе. Используется при обработке свойств
элементов при объявлении класса пользовательской панели задач.(см. [Добавление панелей задач](/api_help/fileman/editor/add_taskbar.php)).

\*В визуальном режиме некоторые фрагменты кода или другие элементы заменяются на их визуальное представление - иконки (пиктограммы). Свойства таких элементов
хранятся в сериализованном виде в качестве атрибута этого элемента. Данный метод десериализует свойства и возвращает их в виде массива.

```
array
oBXEditorUtils.getCustomNodeParams(
	object pNode
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *pNode* | Узел DOM структуры документа **или** объект [BXNodeElement](/api_help/fileman/editor/bxnodeelement.php), передаваемый методу *UnParseElement()* при описании класса пользовательской панели задач (см. [Добавление панелей задач](/api_help/fileman/editor/add_taskbar.php)). |

#### Возвращаемое значение

Возвращает массив. Структура массива, а также его тип (ассоциативный/неассоциативный) зависит от свойств, заданных элементу при создании или в ходе
работы с ним.

#### Смотрите также

* [oBXEditorUtils.setCustomNodeParams()](/api_help/fileman/editor/obxeditorutils/setcustomnodeparams.php)

### Примеры использования

```
<script>
function CustomTaskbar()
{
	var oTaskbar = this;
	
	CustomTaskbar.prototype.OnTaskbarCreate = function ()
	{
		//...
	}
	
	CustomTaskbar.prototype.ShowProperties = function(_bNew, _pTaskbar, _pElement)
	{
		//...
		var arParams = oBXEditorUtils.getCustomNodeParams(_pElement);//Возвращает массив свойств
		//...
	}
	
	CustomTaskbar.prototype.UnParseElement = function(node)
	{
		//...
		var arParams = oBXEditorUtils.getCustomNodeParams(node);//Возвращает массив свойств
		//...
		return false;
	}
}
</script>Копировать
```

Новинки документации в соцсетях:
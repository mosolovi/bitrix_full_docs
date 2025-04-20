[Управление структурой](/api_help/fileman/index.php)

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

setCustomNodeParams

setCustomNodeParams
===================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

Устанавливает свойства "искуственного" элемента\*, переданные в виде массива параметров.
Используется при обработке свойств элементов при объявлении класса пользовательской панели задач.
(см. [Добавление панелей задач](/api_help/fileman/editor/add_taskbar.php)).

\*В визуальном режиме некоторые фрагменты кода или другие элементы заменяются на их визуальное представление - иконки (пиктограммы). Свойства таких элементов
хранятся в сериализованном виде в качестве атрибута этого элемента. Данный метод сериализует массив свойств и сохраняет их.

```
void
oBXEditorUtils.setCustomNodeParams(
	object pNode
	array arParams
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *pNode* | Узел DOM структуры документа **или** объект [BXNodeElement](/api_help/fileman/editor/bxnodeelement.php), передаваемый методу *UnParseElement()* при описании класса пользовательской панели задач (см. [Добавление панелей задач](/api_help/fileman/editor/add_taskbar.php)). |
| *arParams* | Массив свойств. Допускаются ассоциативные и вложенные массивы. |

#### Возвращаемое значение

Ничего не возвращает.

#### Смотрите также

* [oBXEditorUtils.getCustomNodeParams()](/api_help/fileman/editor/obxeditorutils/getcustomnodeparams.php)

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
		var _arParams = oBXEditorUtils.getCustomNodeParams(_pElement);//Возвращает массив свойств
		_arParams['value'] = 'new value';
		//...		
		oBXEditorUtils.setCustomNodeParams(_pElement,_arParams);//Устанавливает массив свойств
		//...
	}
	
	CustomTaskbar.prototype.UnParseElement = function(node)
	{
		//...
		var arParams = oBXEditorUtils.getCustomNodeParams(node);//Возвращает массив свойств
		//...
		arParams['property'] = 'new property';
		//...
		oBXEditorUtils.setCustomNodeParams(node,arParams);//Устанавливает массив свойств
		//...
		return false;
	}
}
</script>Копировать
```

Новинки документации в соцсетях:
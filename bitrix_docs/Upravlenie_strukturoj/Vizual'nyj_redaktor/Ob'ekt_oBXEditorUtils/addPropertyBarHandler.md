[Управление структурой](/api_help/fileman/index.php)

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

addPropertyBarHandler

addPropertyBarHandler
=====================

Включить вкладки

Описание и параметры

Пример

### Описание и параметры

Добавляет обработчик *handler*, который будет вызываться при формировании панели свойств
для элемента с именем тега *tagname*.  
Вызов ("подсветка") панели свойств для элемента происходит автоматически при клике по нему или сразу после вставки элемента,
если он вставляется из пользовательской панели задач.
В качестве второго параметра методу передается функция или метод, формирующая, при необходимости, информационные параметры
элемента, а также реализует возможность их редактирования.
Использование в качестве параметра *handler* анонимных функций нежелательно.

```
void
oBXEditorUtils.addPropertyBarHandler(
	string tagname,
	function handler
);Копировать
```

#### Параметры метода

#### | Параметр | Описание | | --- | --- | | *tagname* | Имя тега, элемента | | *handler* | Функция или метод обработки события инициализации панели свойств. Данной функции при инициализации передается три параметра: | Параметр | Описание | | --- | --- | | bool *bNew* | Равен ***true***, если до этого в панели свойств отображались свойства элемента с таким же именем тега, ***false***, если отображались свойства элемента с другим именем тега. Может использоваться для ускорения процедуры показа свойств: если подряд вызывается процедура показа свойств однотипного элемента, то при повторном показе, элементы управления можно не создавать заново, а только заполнять новыми данными. | | object *pTaskbar* | Ссылка на объект панели свойств. Используется для формирования в ней визуального отображения свойств элемента. Важное свойство, которое может использоваться непосредственно для присоединения элементов управления и отображения: ***pCellProps*** - объект node DOM, является контейнером прокручиваемой области панели свойств. | | object **pElement** | Ссылка на выделенный элемент. Для считывания/изменения свойств элемента можно использовать методы [getCustomNodeParams()](/api_help/fileman/editor/obxeditorutils/getcustomnodeparams.php) и [setCustomNodeParams()](/api_help/fileman/editor/obxeditorutils/setcustomnodeparams.php) глобального объекта [oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php). | |

### Пример

#### Пример добавления обработчика для панели свойств

```
<script>
function CustomTaskbar()
{
	var oTaskbar = this;
	
	CustomTaskbar.prototype.OnTaskbarCreate = function ()
	{
		//...
		//Добавление обработчика панели свойств для элемента "_customtag"
		oBXEditorUtils.addPropertyBarHandler('_customtag',this.ShowProperties);
		//...
	}
	
	//...
	
	CustomTaskbar.prototype.ShowProperties = function(_bNew, _pTaskbar, _pElement)
	{
		// _pTaskbar.pCellProps - прокручиваемая область панели свойств		
		//Считывание свойств элемента
		var arParams = oBXEditorUtils.getCustomNodeParams(_pElement);
		//...
		// операции над свойствами, отображение, изменение
		//...
		//Сохранение свойств элемента
		oBXEditorUtils.setCustomNodeParams(_pElement,arParams);
	}
}
</script>Копировать
```

Новинки документации в соцсетях:
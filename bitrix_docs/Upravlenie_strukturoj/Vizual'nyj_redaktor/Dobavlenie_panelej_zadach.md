[Управление структурой](/api_help/fileman/index.php)

[Визуальный редактор](/api_help/fileman/editor/index.php)

Добавление панелей задач

Добавление панелей задач
========================

Включить вкладки

Объявление класса панели задач

Добавление панели задач

API визуального редактора предусматривает возможность добавления пользовательских панелей задач в визуальный редактор. Данная возможность
позволяет подключить к редактору практически произвольный функционал.
Подключение панели задач происходит в два этапа:

### Объявление класса панели задач

Для объявления класса панели задач необходимо придерживаться стандартных правил описания классов в JavaScript. Учитывая тот факт,
что в синтаксисе языка JavaScript не предусмотрено специального синтаксиса для описания классов, для этих целей используются функции.  
В теле описываемой функции, используя синтаксис объявления функциональных литералов, определяются методы класса, как свойства
объекта ***prototype***.

Для обеспечения взаимодействия с API визуального редактора, при объявлении класса можно использовать:

* обработчики стандартных событий
* свойства класса-родителя
* методы класса-родителя

Объявление **обработчики стандартных событий**, возникающих при взаимодействии пользователя с визуальным редактором и определяемой
панелью задач, позволяет соответствующим образом реагировать на действия пользователя и системные события.

#### Обработчики стандартных событий

| Обработчик | Описание |
| --- | --- |
| **OnTaskbarCreate**() | Выполняется при создании панели задач. Позволяет сформировать визуальное представление панели а также выполнить все подготовительные действия |
| **OnTaskbarRemove**() | Выполняется при удалении панели задач. Может применяться для очистки памяти от созданных объектов, обявленных событий, для предотвращения утечек памяти |
| **OnElementDragEnd**(object *oElement*) | Выполняется при перетаскивании элемента из списка, сформированного методами формирования стандартных панелей задач (ряд методов класса родителя). Параметр **oElement** является экземпляром объекта [BXNodeElement](/api_help/fileman/editor/bxnodeelement.php), наследующим свойства объекта node DOM, кроме того обладающим рядом специальных свойств, позволяющих его однозначно идентифицировать. |
| **UnParseElement**(object *oElement*) | Выполняется при переключении визуального редактора из визуального режима в режим редактирования кода или смешанный режим. Параметр **oElement** является объектом [BXNodeElement](/api_help/fileman/editor/bxnodeelement.php), наследующим ряд свойств объекта node DOM, кроме того обладающим рядом специальных свойств, позволяющих его однозначно идентифицировать.  Возвращает код, на который *следует заменить* искомый элемент, или ***false***, если замена не требуется.   **ВАЖНО!** Данный обработчик вызывается для **каждого** нестандартного визуального элемента, поэтому для нахождения нужного элемента необходимо реализовывать проверку атрибута \_\_bxtagname элемента. Например:  ``` CustomTaskbar.prototype.UnParseElement = function(node) { 	if (node.arAttributes["__bxtagname"] == '__customtag1') 		return '<?MyPHPFunction(0)?>' 	if (node.arAttributes["__bxtagname"] == '__customtag1') 		return '<?MyPHPFunction(1)?>' 	if (node.arAttributes["__bxtagname"] == '__customtag2') 		return '<?MyPHPFunction(2)?>' 	return false; }Копировать ``` |

#### Свойства и методы класса-родителя

Для использования свойств и методов класса-родителя в теле функции, описывающей класс панели задач, необходимо объявить переменную уровня
функции и присвоить ей значение this. В дальнейшем, для обращения к предопределённым методам и свойствам нужно использовать эту переменную.

  
**Например:**

```
function CustomTaskbar()
{
	var oTaskbar = this;
	CustomTaskbar.prototype.OnTaskbarCreate = function ()
	{		
		var pDataCell = oTaskbar.CreateScrollableArea(oTaskbar.pDataCell);
		//......
	}
	//....
}Копировать
```

#### Свойства класса-родителя

| Свойство | Описание |
| --- | --- |
| **pDataCell** | Область панели задач, доступная для формирования интерфейса. |

#### Методы класса-родителя

| Метод | Описание |
| --- | --- |
| object   **CreateScrollableArea(**    object *nodeElement*  **);** | Метод, создающий прокручиваемую область внутри элемента *nodeElement*, являющегося объектом node DOM и возвращает ее в виде ссылки на объект node DOM. |
| bool   **DisplayElementList(**    array *arElements*,    object *oCont*  **);** | Метод создает стандартный список элементов на основе передаваемого ему массива, и прикрепляет его к контейнеру *oCont*, который является объектом node DOM. Возвращает true в случае успешного завершения операции, false - в противном случае. *oCont* не должен содержать других элементов кроме списка.  Передаваемый в качестве параметра массив *arElements* является индексным, каждый его элемент является ассоциативным массивом и имеет следующую структуру:   |  |  | | --- | --- | | **Индекс** | **Описание** | | string *name* | Имя элемента | | string *title* | Название элемента, отображается в списке | | string *tagname* | Имя тега. Используется для отображения данных в панели свойств а также для обработки элемента при переключении в режим просмотра кода | | string *icon* | Путь к файлу иконке, которая будет отображаться в списке | | bool *isGroup* | ***true*** - если элемент является группой;   ***false*** - если элемент не является группой; | | array *params* | Массив параметров. Поддерживаются также ассоциативные и вложенные массивы. | | array *childElements* | Массив, указывается для элементов, являющихся группами. Каждый элемент этого массива также является массивом со структурой, идентичной структуре элемента, описанной в этой таблице. |  Пример создания списка элементов приведен ниже.  \*На текущем этапе поддерживаются структуры описания элементов с двухуровневой вложенностью. |
| bool   **RemoveElementList(**    object *oCont*  **);** | Метод, удаляет список элементов из контейнера *oCont*. Возвращает true в случае успешного завершения операции, false - в противном случае. |
| bool   **AddElement(**    array *oElement*,    object *oCont*,    [string *sPath*],    [int *orderInd*]  **);** | Добавляет элемент в список элементов. Используется для добавления элементов в список. *oElement* - массив имеющий структуру элемента списка(см. метод DisplayElementList()).   *oCont* - контейнер, в котором находится список элементов.  *sPath* - необязательный параметр,определяет глубину вложенности добавляемого элемента путём указания пути, состоящего из перечисленных через запятую имен элементов-групп.Если он не указан или в качестве параметра передана пустая строка, используется самый верхний уровень вложенности.  *orderInd* определяет, каким по порядку будет добавлен элемент на заданый уровень вложенности. Если *orderInd* равен -1 или не задан, элемент вставляется в конец списка.  Возвращает true в случае успешного завершения операции, false - в противном случае. |
| bool   **RemoveElement(**    string *elName*,    object *oCont*,    [string *sPath*]  **);** | Удаляет элемент c именем *elName* из списка элементов, находящегося в контейнере *oCont*.  *sPath* - необязательный параметр,определяет глубину вложенности удаляемого элемента путём указания пути, состоящего из перечисленных через запятую имен элементов-групп.Если он не указан или в качестве параметра передана пустая строка, используется самый верхний уровень вложенности.  Возвращает true в случае успешного завершения операции, false - в противном случае. |

### Использование других методов и средств API

Кроме описанных выше методов класса-родителя, при описании класса панели задач можно использовать определённые методы API визуального
редактора, для упрощения решения стандартных задач.

#### Добавление обработчика элементов для панели свойств

Средствами API можно добавить обработчик для панели свойств визуального редактора, реализуя, таким образом, возможность отображения
и редактирование свойств произвольных элементов.  
Для добавления обработчика для панели свойств необходимо воспользоваться методом [addPropertyBarHandler()](/api_help/fileman/editor/obxeditorutils/addpropertybarhandler.php) глобального объекта [oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php):

### Добавление панели задач

Для добавления обявленной панели задач в визуальный редактор необходимо вызвать метод [addTaskBar](/api_help/fileman/editor/obxeditorutils/addtaskbar.php) глобального объекта [oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php):

#### Описание:

```
void
oBXEditorUtils.addTaskBar(
	string className,
	int taskbarSetPos,
	string taskbarTitle,
	array params
);Копировать
```

Более подробное описание метода приведено в его [описании](/api_help/fileman/editor/obxeditorutils/addtaskbar.php).
**Параметры:**

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
	var pDataCell;
	var oTaskbar = this;
	
	CustomTaskbar.prototype.OnTaskbarCreate = function ()
	{
		//Создание прокручиваемой области
		pDataCell = oTaskbar.CreateScrollableArea(oTaskbar.pDataCell);
		//Добавление обработчика панели свойств для элемента "_customtag2"
		oBXEditorUtils.addPropertyBarHandler('_customtag2',this.ShowProperties);
		//Отображение списка элементов
		this.DisplayTree();
	}
	
	CustomTaskbar.prototype.DisplayTree = function()
	{
		//Создание массива элементов
		var arElements = [];
		var _arElement = [];
		_arElement['name'] = 'group1';
		_arElement['title'] = 'Group 1';
		_arElement['tagname'] = '';
		_arElement['icon'] = '';
		_arElement['isGroup'] = true;
		_arElement['params'] = [];	
		_arElement['childElements'] = [];
			var __arElement = [];
			__arElement['name'] = 'el_1_1';
			__arElement['title'] = 'Element 1.1';
			__arElement['tagname'] = '_customtag';
			__arElement['icon'] = '/images/icon1.gif';
			__arElement['isGroup'] = false;
			__arElement['params'] = [];
			__arElement['childElements'] = [];
			_arElement['childElements'].push(__arElement);
			
			__arElement = [];
			__arElement['name'] = 'el_1_2';
			__arElement['title'] = 'Element 1.2';
			__arElement['tagname'] = '_customtag2';
			__arElement['icon'] = '/images/icon2.gif';
			__arElement['isGroup'] = false;
			
				___arPar = [];
				___arPar[0] = {name:'param0',title:'Параметр0',value:'value0'};
				___arPar[1] = {name:'param1',title:'Параметр1',value:'value1'};
				___arPar[2] = {name:'param2',title:'Параметр2',value:'value2'};			
			__arElement['params'] = ___arPar;
			__arElement['childElements'] = [];			
			
			_arElement['childElements'].push(__arElement);
			
		arElements.push(_arElement);
		
		_arElement = [];
		_arElement['name'] = 'el_2';
		_arElement['title'] = 'Element 2';
		_arElement['tagname'] = '_customtag';
		_arElement['icon'] = '/images/icon3.gif';
		_arElement['params'] = [];
		_arElement['isGroup'] = false;
		_arElement['childElements'] = [];
		arElements.push(_arElement);
		
		//Добавление списка элементов к прокручиваемой области
		oTaskbar.DisplayElementList(arElements,pDataCell);
	}
	
	//Обработчик панели свойств для элемента _customtag2
	CustomTaskbar.prototype.ShowProperties = function(_bNew, _pTaskbar, _pElement)
	{
		// _pTaskbar.pCellProps - прокручиваемая область панели свойств	
		var arParams = oBXEditorUtils.getCustomNodeParams(_pElement);
		var _input,_div;
		var __saveParams = function(e)
		{
			for (var _i=0; _i<arParams.length;_i++)
			{
				_input = document.getElementById('__param_'+arParams[_i].name);				
				arParams[_i].value = _input.value;
			}
			
			//oBXEditorUtils.setCustomNodeParams(_pElement,arParams);
		}
		
		if (_bNew)
		{
			oBXEditorUtils.BXRemoveAllChild(_pTaskbar.pCellProps);
			for (var _i=0;_i<arParams.length;_i++)
			{		
				_input = document.createElement('INPUT');
				_input.type = 'text';
				_input.id = '__param_'+arParams[_i].name;
				_input.value = arParams[_i].value;
				_input.onblur = __saveParams;
				
				_div = document.createElement('DIV');
				_div.id = '__vd_'+arParams[_i].name;
				_div.innerHTML = arParams[_i].title;				
				_div.appendChild(_input);
				_pTaskbar.pCellProps.appendChild(_div);
			}
		}
		else
		{
			for (var _i=0;_i<arParams.length;_i++)
			{	
				_input = document.createElement('INPUT');
				_input.type = 'text';
				_input.id = '__param_'+arParams[_i].name;
				_input.value = arParams[_i].value;
				_input.onblur = __saveParams;
				
				_div = document.getElementById('__vd_'+arParams[_i].name);
				_div.innerHTML = arParams[_i].title;				
				_div.appendChild(_input);
			}
		}
	}
	
	CustomTaskbar.prototype.UnParseElement = function(node)
	{
		if (node.arAttributes["__bxtagname"] == '_customtag')
			return '<?SomeSuperFunction(3)?>'
		if (node.arAttributes["__bxtagname"] == '_customtag2')
			return '<?SomeSuperFunction(1)?>'
	
		return false;
	}
	
	CustomTaskbar.prototype.OnElementDragEnd = function(oEl)
	{
		if (oEl.getAttribute('__bxtagname') == '_customtag')
		{
			oEl.parentNode.removeChild(oEl);
			oTaskbar.insertHTML('snippet');
			alert('Был вставлен произвольный элемент');
		}
		else if(oEl.getAttribute('__bxtagname') == '_customtag2')
			alert('Был вставлен другой произвольный элемент');
	}
}
//Добавление панели задач
oBXEditorUtils.addTaskBar('CustomTaskbar',2,"Help",[]);
</script>Копировать
```

Новинки документации в соцсетях:
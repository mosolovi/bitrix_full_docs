[Управление структурой](/api_help/fileman/index.php)

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

addDOMHandler

addDOMHandler
=============

Добавляет функцию-обработчик для обработки содержимого документа как DOM-структуры.
Функции, добавленные таким образом, могут обращаться к узлам редактируемого документа(в визуальном режиме),
при загрузке редактируемого документа, а также при переключении из режима кода, в WYSIWYG.  
Обрабатывают документ после его обработки функциями, добавленными при помощи методов addContentParser и addPHPParser.

```
void
oBXEditorUtils.addDOMHandler(
	function handler[,
	int orderInd]
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| **handler** | Функция, объявленная в глобальной области видимости.  В качестве единственного параметра принимает ссылку на объект document редактируемого документа. Ничего не возвращает. |

#### Пример

```
function myDOMHandler(oDocument)
{
	//манипуляции с документом
	var arIMG = oDocument.getElementsByTagName('IMG');
	var iLen = arIMG.length;
	for (var i=0;i>iLen;i++)
		arIMG[i].src = 'my_new_image.jpg';
}
//Добавление обработчика
oBXEditorUtils.addDOMHandler(myDOMHandler);Копировать
```

Данный обработчик позволяет заменить атрибут src всех рисунков в документе на my\_new\_image.jpg (оставляя при этом остальные атрибуты нетронутыми)

Новинки документации в соцсетях:
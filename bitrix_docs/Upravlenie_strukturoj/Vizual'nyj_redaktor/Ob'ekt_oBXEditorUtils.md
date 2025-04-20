[Управление структурой](/api_help/fileman/index.php)

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

Глобальный объект oBXEditorUtils

Глобальный объект oBXEditorUtils
================================

Для эффективного решения задач взаимодействия с API визуального редактора предусмотрен глобальный объект **oBXEditorUtils**.
Этот объект и его подобъекты обладают рядом свойств и методов, позволяющих использовать существующий предоставляемый функционал API редактора.
Задачи и параметры, привязанные к определённым структурным единицам редактора, могут быть реализованны в виде методов и свойств класса-родителя
или методов других глобальных объектов API визуального редактора.

### Методы

| Метод | Описание |
| --- | --- |
| [addContentParser](/api_help/fileman/editor/obxeditorutils/addcontentparser.php) | Добавляет функцию-обработчик для обработки содержимого документа в виде исходного кода. |
| [addPHPParser](/api_help/fileman/editor/obxeditorutils/addphpparser.php) | Добавляет функцию-обработчик для обработки всех фрагментов PHP из исходного кода документа. |
| [addDOMHandler](/api_help/fileman/editor/obxeditorutils/adddomhandler.php) | Добавляет функцию-обработчик для обработки содержимого документа как DOM-структуры. |
| [addPropertyBarHandler](/api_help/fileman/editor/obxeditorutils/addpropertybarhandler.php) | Добавляет обработчик, который вызывается при формировании панели свойств для элемента с определённым именем тега. |
| [addTaskBar](/api_help/fileman/editor/obxeditorutils/addtaskbar.php) | Добавляет панель управления. |
| [BXRemoveAllChild](/api_help/fileman/editor/obxeditorutils/bxremoveallchild.php) | Удаляет дочерние узлы элемента. |
| [getCustomNodeParams](/api_help/fileman/editor/obxeditorutils/getcustomnodeparams.php) | Возвращает массив параметров "искуственных" элементов, заменяющих определённые фрагменты кода в визуальном режиме. |
| [setCustomNodeParams](/api_help/fileman/editor/obxeditorutils/setcustomnodeparams.php) | Записывает массив параметров "искуственных" элементов, заменяющих определённые фрагменты кода в визуальном режиме. |

### Подобъекты

| Подобъект | Описание |
| --- | --- |
| [PHPParser](/api_help/fileman/editor/obxeditorutils/phpparser/index.php) | Добавляет функцию-обработчик для обработки содержимого документа в виде исходного кода. |

Новинки документации в соцсетях:
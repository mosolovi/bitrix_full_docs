[Управление структурой](/api_help/fileman/index.php)

[Визуальный редактор](/api_help/fileman/editor/index.php)

Объект BXNodeElement

Объект BXNodeElement
====================

Экземпляры объекта BXNodeElement передаются в качестве параметра обработчикам событий при описании
пользовательских панелей задач. Класс этого объекта используется для внутреннего представления "искуственных" элементов,
используемых для замены некоторых фрагментов кода на иконки в визуальном режиме.

### Свойства

| Метод | Описание |
| --- | --- |
| **arAttributes** | Массив, содержит два важных элемента  | Индекс | Описание | | --- | --- | | **\_\_bxtagname** | Содержит искуственное имя тега, которое задается при создании искуственного элемента | | **\_\_bxcontainer** | Содержит сериализованное представление параметров элемента. | |

### Пример

```
//....
//pNode - экземпляр объекта BXNodeElement
alert(pNode.arAttributes["__bxtagname"]);
//....
Копировать
```

Сведения об остальных свойствах объекта будут предоставлены позднее.

Новинки документации в соцсетях:
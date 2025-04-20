[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

addToFavorite (15.6.0)

addToFavorite
=============

```
public function addToFavorite($parameters = array('AFFECT_CHILDREN' => true))Копировать
```

Данный метод добавляет задачу в **Избранное**

#### Параметры

| Параметр | Описание |
| --- | --- |
| *PARAMETERS* | Массив, содержащий ключ *AFFECT\_CHILDREN*. Если значение ключа *true*, то в **Избранное** также будут добавлены и подзадачи данной задачи. Если *false*, то они включены не будут. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного добавления, в противном случае возвращает *false*.

#### Пример использования

```
// добавление в избранное 
$task = new CTaskItem(10, $GLOBALS['USER']->GetId()); 
$task->addToFavorite(); Копировать
```

Новинки документации в соцсетях:
[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

deleteFromFavorite (15.6.0)

deleteFromFavorite
==================

```
public function deleteFromFavorite($parameters = array('AFFECT_CHILDREN' => true))Копировать
```

Данный метод удаляет задачу из **Избранного**.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *PARAMETERS* | Массив, содержащий ключ *AFFECT\_CHILDREN*. Если значение ключа *true*, то в **Избранное** также будут добавлены и подзадачи данной задачи. Если *false*, то они включены не будут. |

#### Возвращаемое значение

Метод возвращает *true* в случае удаления добавления, в противном случае возвращает *false*.

#### Пример использования

```
// удаление из избранного 
$task = new CTaskItem(10, $GLOBALS['USER']->GetId()); 
$task->deleteFromFavorite();Копировать
```

Новинки документации в соцсетях:
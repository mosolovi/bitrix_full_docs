[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

toggleFavorite (15.6.0)

toggleFavorite
==============

```
public function toggleFavorite()Копировать
```

Данный метод меняет для указанной задачи состояние избранности.

#### Возвращаемое значение

Возвращает *true*, если задача изначально не была в избранном. В противном случае возвращает *false*.

#### Пример использования

```
// переключение состояния избранности 
$task = new CTaskItem(10, $GLOBALS['USER']->GetId()); 
$task->toggleFavorite();Копировать
```

Новинки документации в соцсетях:
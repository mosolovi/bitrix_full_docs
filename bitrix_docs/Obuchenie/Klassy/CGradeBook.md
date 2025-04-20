[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CGradeBook](/api_help/learning/classes/cgradebook/index.php)

Класс CGradeBook (доступен с 5.1.0)

Класс CGradeBook
================

**CGradeBook** - класс для работы с журналом.

| Метод | Описание | С версии |
| --- | --- | --- |
| [GetList](/api_help/learning/classes/cgradebook/getlist.php) | Возвращает список записей журнала по фильтру. | 5.1.0 |
| [GetByID](/api_help/learning/classes/cgradebook/getbyid.php) | Возвращает запись по идентификатору. | 5.1.0 |
| [Add](/api_help/learning/classes/cgradebook/add.php) | Добавляет новую запись в журнал. | 5.1.0 |
| [Update](/api_help/learning/classes/cgradebook/update.php) | Изменяет параметры записи в журнале. | 5.1.0 |
| [Delete](/api_help/learning/classes/cgradebook/delete.php) | Удаляет запись из журнала. | 5.1.0 |

#### Пример использования

```
// пример пересчета журнала
$gradebook = new CGradeBook; 
$gradebook->RecountAttempts($STUDENT_ID,$TEST_ID); 
Копировать
```

Новинки документации в соцсетях:
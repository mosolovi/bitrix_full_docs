[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

GetEmailStatuses (доступен с 8.5.3)

GetEmailStatuses
================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CPosting::GetEmailStatuses(
	int ID
);Копировать
```

Метод возвращает массив статусов в очереди выпуска на отправку. Ключами массива являются статусы, а значениями количество подписчиков в соответствующих статусах. Метод статический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор выпуска |  |

#### Возвращаемое значение

Массив распределения получателей выпуска по статусам. Если получатели в каком-то из статусов отсутствуют, то и соответствующий элемента массива будет отсутствовать.

Допустимыми значениями ключей являются:

* "N" - письмо отправлено успешно;
* "E" - отправлено с ошибкой;
* "Y" - ожидает отправки.

### Смотрите также

* [Поля CPosting](/api_help/subscribe/classes/cpostinggeneral/cpostingfields.php)

### Примеры использования

```
<?
$arStatuses = CPosting::GetEmailStatuses($ID);
if(!isset($arStatuses["Y"]))
	echo "Выпуск отправлен.";
?>Копировать
```

Новинки документации в соцсетях:
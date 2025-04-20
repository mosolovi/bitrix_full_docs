[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnExternalAuthList (с версии 4.0.6)

OnExternalAuthList
==================

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
array
функция-обработчик();Копировать
```

Событие "OnExternalAuthList" вызывается для получения списка источников внешней авторизации при вызове метода [CUser::GetExternalAuthList](/api_help/main/reference/cuser/getexternalauthlist.php).

#### Параметры

Без параметров.

#### Возвращаемое значение

Массив вида `Array(Array("ID"=>"Код источника 1", "NAME"=>"Название источника 1"), ...)` .   

#### Смотрите также

* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [CUser::GetExternalAuthList](/api_help/main/reference/cuser/getexternalauthlist.php)
* [Внешняя авторизация](http://dev.1c-bitrix.ru/learning/course/index.php?&COURSE_ID=43&LESSON_ID=3574)

### Пример функции-обработчика

```
<?
AddEventHandler("main", "OnExternalAuthList", Array("__IPBAuth", "OnExternalAuthList"));
class __IPBAuth
{
	public static function OnExternalAuthList()
	{
		return Array(
		Array("ID"=>"IPB", "NAME"=>"Invision Power Board")
		);
	}
}
?>Копировать
```

Новинки документации в соцсетях:
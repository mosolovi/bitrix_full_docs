[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Утилиты](/api_help/js_lib/kernel/utilits/index.php)

BX.getCookie (с версии 16.5.3)

BX.getCookie
============

```
result_type
BX.getCookie(
	name
);Копировать
```

Возвращает значение cookie с именем name.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| name | Имя |

#### Примеры использования

```
document.cookie = 'test=123456';
BX.getCookie('test'); // вернет - 123456Копировать
```

Новинки документации в соцсетях:
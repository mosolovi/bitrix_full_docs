[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Утилиты](/api_help/js_lib/kernel/utilits/index.php)

BX.namespace

BX.namespace
============

```
object BX.namespace(
	string namespace
)Копировать
```

Создает пространство имен в глобальной объекте BX. Если пространство имен уже существует функция ничего не делает.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| namespace | Название создаваемого пространства имён. |

#### Возвращаемое значение

Возвращает ссылку на последний элемент цепочки имен.

#### Примеры использования

```
BX.namespace("MyCompany.Module.NewsForm");
Создаст объект MyCompany в глобальном объекте BX следующего вида:
BX.MyCompany = {
	Module: {
		NewsForm: {
		}
	}
}Копировать
```

Новинки документации в соцсетях:
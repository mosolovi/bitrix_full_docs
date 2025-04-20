[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingTemplate](/api_help/subscribe/classes/cpostingtemplate/index.php)

GetByID (доступен с 4.0.5)

GetByID
=======

```
array
CPostingTemplate::GetByID(
	string path = ""
);Копировать
```

Метод возвращает шаблон по его идентификатору (относительному пути). Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| path | Относительный путь к каталогу шаблона. |  |

#### Возвращаемые значения

Возвращается массив формируемый в файле description.php дополненный элементом "path" равным относительному пути к каталогу шаблона.

#### Пример файла description.php

```
<?
$arTemplate =
	Array(
		"NAME"=>"Дайджест новостей",
		"DESCRIPTION"=>"Шаблон генерации дайджеста новостей."
	);
?>Копировать
```

Новинки документации в соцсетях:
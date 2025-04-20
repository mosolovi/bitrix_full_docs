[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingTemplate](/api_help/subscribe/classes/cpostingtemplate/index.php)

IsExists (доступен с 4.0.5)

IsExists
========

```
bool
CPostingTemplate::IsExists(
	string path = ""
);Копировать
```

Метод проверяет существование каталога шаблона. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| path | Относительный путь к каталогу шаблона. |  |

#### Возвращаемые значения

true, если каталог шаблона существует, и false в противном случае.

#### Пример использования

```
<?
if(!CPostingTemplate::IsExists("bitrix/php_interface/subscribe/templates/news"))
	echo "Указанный шаблон не существует.";
?>Копировать
```

Новинки документации в соцсетях:
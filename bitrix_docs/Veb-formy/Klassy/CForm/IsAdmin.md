[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

IsAdmin (4.0.4)

IsAdmin
=======

```
bool
CForm::IsAdmin()Копировать
```

Возвращает "true", если текущий пользователь имеет административные [права](/api_help/form/permissions.php#module) на модуль **Веб-формы**, в противном случае - "false". Метод нестатический.

#### Параметры метода

Без параметров.

#### Смотрите также

* [Права на модуль](/api_help/form/permissions.php#module)

#### Примеры использования

```
<?
if (CForm::IsAdmin())
{
	echo "У вас административные права на модуль Веб-форм.";
}
?>Копировать
```

Новинки документации в соцсетях:
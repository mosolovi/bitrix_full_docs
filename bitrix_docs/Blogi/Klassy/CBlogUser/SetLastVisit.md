[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUser](/api_help/blogs/classes/cbloguser/index.php)

SetLastVisit (5.0.2)

SetLastVisit
============

```
bool
CBlogUser::SetLastVisit(
);Копировать
```

Метод регистрирует последнее посещение блога текущим пользователем. Метод статический.

#### Возвращаемое значение

Метод возвращает *true* в случае успешной регистрации посещения, в противном случае возвращает *false*.

#### Примеры использования

```
<?
if(!CBlogUser::SetLastVisit())
	echo 'Ошибка!';
?>Копировать
```

Новинки документации в соцсетях:
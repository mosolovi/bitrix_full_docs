[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUser](/api_help/blogs/classes/cbloguser/index.php)

GetUserIP (5.0.2)

GetUserIP
=========

```
string
CBlogUser::GetUserIP();Копировать
```

Метод возвращает IP-адреса текущего посетителя. Метод статический.

#### Возвращаемое значение

Возвращается массив с доступными IP.

#### Примеры использования

```
<?
	$userIP = CBlogUser::GetUserIP();
	print_r($userIP);
?>Копировать
```

Новинки документации в соцсетях:
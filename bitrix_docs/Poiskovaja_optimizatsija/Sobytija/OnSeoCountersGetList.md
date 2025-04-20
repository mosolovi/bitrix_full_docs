[Поисковая оптимизация](/api_help/seo/index.php)

[События](/api_help/seo/events/index.php)

OnSeoCountersGetList (доступно с 8.5.1)

OnSeoCountersGetList
====================

```
функция-обработчик();Копировать
```

Событие **OnSeoCountersGetList** предназначено для подключения собственного программного счетчика.

#### Пример использования

```
public static function MyOnSeoCountersGetList() 
{ 
	$value = rand(100, 500); 
	return  
		'<div style="width: 150px; text-align: center; border: solid 1px red; margin: 1px; padding: 5px;">Тестовый счетчик: <b>'.$value.'</b></div>' 
		'<!--/Start webdew.ro/--><a href="http://www.webdew.ro/utils.php"><img src="http://www.webdew.ro/pagerank/free-pagerank-display.php?a=getCode&s=goo" title="Free PageRank Display Code" border="0px" alt="PageRank" /></a><!--/End webdew.ro/-->'; 
} 
 
addEventHandler('seo', 'OnSeoCountersGetList', 'MyOnSeoCountersGetList');Копировать
```

Новинки документации в соцсетях:
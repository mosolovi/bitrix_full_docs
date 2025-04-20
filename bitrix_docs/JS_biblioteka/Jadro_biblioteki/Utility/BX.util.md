[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Утилиты](/api_help/js_lib/kernel/utilits/index.php)

BX.util

BX.util
=======

Сборник функций-утилит.

| Функция | Описание | С версии |
| --- | --- | --- |
| BX.util.array\_values()  BX.util.array\_keys()  BX.util.array\_merge()  BX.util.array\_unique()  BX.util.in\_array()  BX.util.array\_search()  BX.util.trim()  BX.util.htmlspecialchars()  BX.util.htmlspecialcharsback()  BX.utill.preg\_quote()  BX.util.str\_pad()  BX.util.strip\_tags() | Аналоги функций PHP. |  |
| BX.util.urlencode() | Кодирует посредством encodeURIComponent, что приводит к некорректной декодировке на сайтах не в UTF. Для корректного приема закодированных таким образом данных на сервере можно выполнить функцию CUtil::JSPostUnescape, которая декодирует глобальные массивы $\_GET, $\_POST и $\_REQUEST. |  |
| ``` Array  BX.util.deleteFromArray( 	array arr, 	int index );Копировать ``` | Удаление элемента из массива с последующим сдвигом ключей. |  |
| ``` Array  BX.util.insertIntoArray( 	array arr, 	int index );Копировать ``` | Вставка элемента в массив с последующим сдвигом ключей. |  |
| ``` BX.util.popup( 	string url, 	int width, 	int height );Копировать ``` | Показ попапа, спозиционированного по центру. |  |

Новинки документации в соцсетях:
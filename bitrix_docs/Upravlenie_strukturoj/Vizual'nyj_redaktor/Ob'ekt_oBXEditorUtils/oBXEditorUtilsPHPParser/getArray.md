...

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

[oBXEditorUtils::PHPParser](/api_help/fileman/editor/obxeditorutils/phpparser/index.php)

getArray

getArray
========

Принимает в качестве аргумента строку, в формате ***Array([параметры])***. Возвращает массив параметров, переданных в строке, или пустой
массив, при отсутствии параметров. Корректно обрабатывает вложенные и ассоциативные массивы, возвращая соответсвующую структуру.
Может использоваться для упрощения анализа фрагмента PHP-кода при создании [PHP-парсера](/api_help/fileman/editor/obxeditorutils/addphpparser.php).

```
array
oBXEditorUtils.PHPParser.getArray(
	string sCode
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *sCode* | Строка, в формате ***Array([параметры])*** |

#### Возвращаемое значение

Возвращает массив. Структура массива зависит от входного параметра.

#### Пример использования

```
<script>
var sCode = 'array("LID"=>"en","TEXT"=>"text text text","PAYED"=>"N","CANCELED"=>"N")';
	   
arParams = oBXEditorUtils.PHPParser.getArray(sCode); 
//arParams["LID"] = "en";
//arParams["TEXT"] = "text text text";
//arParams["PAYED"] = "N";
//arParams["CANCELED"] ="N";
</script>Копировать
```

Новинки документации в соцсетях:
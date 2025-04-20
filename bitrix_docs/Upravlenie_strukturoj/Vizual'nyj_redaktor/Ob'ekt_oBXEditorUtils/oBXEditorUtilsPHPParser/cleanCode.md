...

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

[oBXEditorUtils::PHPParser](/api_help/fileman/editor/obxeditorutils/phpparser/index.php)

cleanCode

cleanCode
=========

Удаляет из PHP-кода комментарии, переводы новой строки, незначащие пробелы. Может использоваться для упрощения анализа фрагмента PHP-кода при создании [PHP-парсера](/api_help/fileman/editor/obxeditorutils/addphpparser.php).

```
string
oBXEditorUtils.PHPParser.cleanCode(
	string sCode
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *sCode* | Строка, содержащая фрагмент php-кода. |

#### Возвращаемое значение

Возвращает строку.

#### Пример использования

```
<script>
var sCode = '$arFields   =   array('+
	'"LID" => "en", //язык'+
	'"TEXT" => "text text text", //текст'+
	'"PAYED" => "N",'+
	'"CANCELED" => "N"'+
	');'
	   
sCode = oBXEditorUtils.PHPParser.cleanCode(sCode); 
//sCode = '$arFields=array("LID"=>"en","TEXT"=>"text text text","PAYED"=>"N","CANCELED"=>"N")';
</script>Копировать
```

Новинки документации в соцсетях:
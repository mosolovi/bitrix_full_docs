...

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

[oBXEditorUtils::PHPParser](/api_help/fileman/editor/obxeditorutils/phpparser/index.php)

parseFunction

parseFunction
=============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

Принимает в качестве аргумента строку, содержащую вызов php-функции в формате ***MyFunction([params])***, и возвращает имя функции
и строку с передаваемыми ей параметрами.  
Может использоваться для упрощения анализа фрагментов PHP-кода при создании [PHP-парсера](/api_help/fileman/editor/obxeditorutils/addphpparser.php).

```
object
oBXEditorUtils.PHPParser.parseFunction(
	string sCode
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *sCode* | Строка, в формате ***MyFunction([params])*** |

#### Возвращаемое значение

Возвращает объект  
**Свойства:**

| Свойство | Описание |
| --- | --- |
| string *name* | Имя функции |
| string *params* | Строка, содержащая параметры передаваемые функции при вызове |

Если строка не соответствует указанному формату, возвращается значение ***false***.

#### Смотрите также

* [parseParameters](/api_help/fileman/editor/obxeditorutils/phpparser/parseparameters.php)

### Примеры использования

```
<script>
var sCode = 'MyPHPFunction("param",$var)';
	   
var oFunc = oBXEditorUtils.PHPParser.parseFunction(sCode); 
//oFunc.name = 'MyPHPFunction';
//oFunc.params = '"param",$var';
</script>Копировать
```

Новинки документации в соцсетях:
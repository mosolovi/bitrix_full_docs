...

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

[oBXEditorUtils::PHPParser](/api_help/fileman/editor/obxeditorutils/phpparser/index.php)

parseParameters

parseParameters
===============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

Принимает в качестве аргумента строку, содержащую параметры (функции), перечисленные через запятую; и возвращает
массив, соответствующий по структуре массиву, переданному в качестве параметра.  
Корректно обрабатывает массивы, в том числе ассоциативные и вложенные.  
Может использоваться для обработки параметров средствами JavaScript при упрощении анализа фрагментов
PHP-кода при создании [PHP-парсера](/api_help/fileman/editor/obxeditorutils/addphpparser.php).

```
array
oBXEditorUtils.PHPParser.parseParameters(
	string sCode
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *sCode* | Строка, в формате ***param1[,param2[,...,paramN]]*** |

#### Возвращаемое значение

Возвращает массив.

#### Смотрите также

* [getParams](/api_help/fileman/editor/obxeditorutils/phpparser/getparams.php)
* [parseParameters](/api_help/fileman/editor/obxeditorutils/phpparser/parseparameters.php)
* [parseFunction](/api_help/fileman/editor/obxeditorutils/phpparser/parsefunction.php)

### Примеры использования

```
<script>
var sCode = '2,"Y",Array(1,2,"string1"),Array("name"=>"SomeName","id"=>$phpVar)';
	   
arParams = oBXEditorUtils.PHPParser.parseParameters(sCode);
//arParams[0] = 2;
//arParams[1] = "Y";
//arParams[2][0] = 1;
//arParams[2][1] = 2;
//arParams[2][2] = "string";
//arParams[3]["name"] = "SomeName";
//arParams[3]["id"] = "$phpVar";
</script>Копировать
```

Новинки документации в соцсетях:
...

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

[oBXEditorUtils::PHPParser](/api_help/fileman/editor/obxeditorutils/phpparser/index.php)

getParams

getParams
=========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

Принимает в качестве аргумента строку, содержащую параметры (функции, или любые другие данные), перечисленные через запятую, и возвращает
массив строковых значений.  
НЕ ОБРАБАТЫВАЕТ массивы, т.е. все данные воспринимаются как строки.  
Может использоваться для упрощения анализа фрагментов PHP-кода при создании [PHP-парсера](/api_help/fileman/editor/obxeditorutils/addphpparser.php).

```
array
oBXEditorUtils.PHPParser.getParams(
	string sCode
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *sCode* | Строка, в формате ***param1[,param2[,...,paramN]]*** |

#### Возвращаемое значение

Возвращает массив строковых значений.

#### Смотрите также

* [parseParameters](/api_help/fileman/editor/obxeditorutils/phpparser/parseparameters.php)

### Примеры использования

```
<script>
var sCode1 = '2,"text text text",5,"N"';
var sCode2 = 'array("LID"=>"en","TEXT"=>"text text text","PAYED"=>"N","CANCELED"=>"N")';
	   
arParams1 = oBXEditorUtils.PHPParser.getArray(sCode1); 
//arParams[0] = '2';
//arParams[1] = '"text text text"';
//arParams[2] = '5';
//arParams[3] = '"N"';
arParams2 = oBXEditorUtils.PHPParser.getArray(sCode2); 
//arParams[0] = 'array("LID"=>"en"';
//arParams[1] = '"TEXT"=>"text text text"';
//arParams[2] = '"PAYED"=>"N"';
//arParams[3] = '"CANCELED"=>"N")';
</script>Копировать
```

Новинки документации в соцсетях:
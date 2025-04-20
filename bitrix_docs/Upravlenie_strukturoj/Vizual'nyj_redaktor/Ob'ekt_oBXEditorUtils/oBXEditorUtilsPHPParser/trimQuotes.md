...

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

[oBXEditorUtils::PHPParser](/api_help/fileman/editor/obxeditorutils/phpparser/index.php)

trimQuotes

trimQuotes
==========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

Возвращает переданный в качестве параметра фрагмент кода без двойных или одинарных кавычек(или другого символа) с начала и конца.
Если фрагмент не содержит кавычек, он возвращается без изменений.

Может использоваться для упрощения анализа фрагментов PHP-кода при создании [PHP-парсера](/api_help/fileman/editor/obxeditorutils/addphpparser.php).

```
string
oBXEditorUtils.PHPParser.trimQuotes(
	string sCode[,
	string cSym]
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *sCode* | Строка, фрагмент PHP-кода |
| *cSym* | Необязательный параметр. Символ, который необходимо удалить. По умолчанию удаляются одинарные или двойные кавычки. |

#### Возвращаемое значение

Возвращает строку.

#### Смотрите также

* [trimPHPTags](/api_help/fileman/editor/obxeditorutils/phpparser/trimphptags.php)

### Примеры использования

```
<script>
var sCode1 = '"My String"';
sCode1 = oBXEditorUtils.PHPParser.trimQuotes(sCode1);//sCode1 = 'My String';
var sCode2 = "'My String'";
sCode2 = oBXEditorUtils.PHPParser.trimQuotes(sCode2);//sCode2 = "My String";
var sCode3 = '-My String-';
sCode3 = oBXEditorUtils.PHPParser.trimQuotes(sCode3,'-');//sCode3 = 'My String';
</script>Копировать
```

Новинки документации в соцсетях:
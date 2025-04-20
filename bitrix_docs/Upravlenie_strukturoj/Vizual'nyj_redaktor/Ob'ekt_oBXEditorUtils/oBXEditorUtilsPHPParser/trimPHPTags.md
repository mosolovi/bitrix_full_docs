...

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

[oBXEditorUtils::PHPParser](/api_help/fileman/editor/obxeditorutils/phpparser/index.php)

trimPHPTags

trimPHPTags
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

Возвращает переданный в качестве параметра фрагмент кода без php-тегов <?php ?> или <? ?>
Если фрагмент не содержит PHP-тегов, строка возвращается без изменений.  
Может использоваться для упрощения анализа фрагментов PHP-кода при создании [PHP-парсера](/api_help/fileman/editor/obxeditorutils/addphpparser.php).

```
string
oBXEditorUtils.PHPParser.trimPHPTags(
	string sCode
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *sCode* | Строка, фрагмент PHP-кода |

#### Возвращаемое значение

Возвращает строку.

#### Смотрите также

* [trimQuotes](/api_help/fileman/editor/obxeditorutils/phpparser/trimquotes.php)

### Примеры использования

```
<script>
var sCode = '<?php MyPHPFunction(); ?>';
sCode = oBXEditorUtils.PHPParser.trimPHPTags(sCode);//sCode = ' MyPHPFunction(); ';
</script>Копировать
```

Новинки документации в соцсетях:
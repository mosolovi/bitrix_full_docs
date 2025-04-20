...

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

[oBXEditorUtils::PHPParser](/api_help/fileman/editor/obxeditorutils/phpparser/index.php)

Вложенный объект oBXEditorUtils.PHPParser

Вложенный объект oBXEditorUtils.PHPParser
=========================================

Вложенный объект **PHPParser** глобального объекта  **oBXEditorUtils** объединяет методы, используемые для облегчения создания PHP-парсера (см. [oBXEditorUtils.addPHPParser()](/api_help/fileman/editor/obxeditorutils/addphpparser.php))

### Методы

| Метод | Описание |
| --- | --- |
| [**cleanCode**](/api_help/fileman/editor/obxeditorutils/phpparser/cleancode.php) | Удаляет из PHP-кода комментарии, переводы новой строки, незначащие пробелы. |
| [**getArray**](/api_help/fileman/editor/obxeditorutils/phpparser/getarray.php) | Принимает в качестве аргумента строку, в формате ***Array([параметры])*** Возвращает массив этих параметров или пустой массив при их отсутствии. Обрабатывает также ассоциативные и вложенные массивы. |
| [**getParams**](/api_help/fileman/editor/obxeditorutils/phpparser/getparams.php) | Обрабатывает строку с перечисленными через запятую параметрами, и возвращает их в виде массива. НЕ ОБРАБАТЫВАЕТ массивы в качестве параметров. |
| [**parseFunction**](/api_help/fileman/editor/obxeditorutils/phpparser/parsefunction.php) | Обрабатывает строку, содержащую вызов php-функции, и возвращает имя функции и строку с передаваемыми ей параметрами. |
| [**parseParameters**](/api_help/fileman/editor/obxeditorutils/phpparser/parseparameters.php) | Обрабатывает строку с перечисленными через запятую параметрами, и возвращает их в виде массива. Обрабатывает массивы в качестве параметров. |
| [**trimPHPTags**](/api_help/fileman/editor/obxeditorutils/phpparser/trimphptags.php) | Возвращает переданный в качестве параметра фрагмент кода (без php-тегов  **<?php ... ?>** или  **<? ... ?>**). |
| [**trimQuotes**](/api_help/fileman/editor/obxeditorutils/phpparser/trimquotes.php) | Возвращает переданный в качестве параметра фрагмент кода без двойные или одинарных кавычек(или другого символа) с начала и конца. |

Новинки документации в соцсетях:
[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnStartIBlockElementUpdate (доступно с 7.1.8)

OnStartIBlockElementUpdate
==========================

```
bool функция-обработчик(
	array &arParams 
);Копировать
```

Событие вызывается в методе [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php) до изменения элемента информационного блока перед проверкой правильности заполнения полей, и может быть использовано для переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/iblock/fields.php#felement) изменяемого элемента информационного блока. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Если в обработчике события *OnStartIBlockElementUpdate* вернуть *false*, то будет отменено выполнение других обработчиков в методе [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php).
  

#### Смотрите также

* [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

Новинки документации в соцсетях:
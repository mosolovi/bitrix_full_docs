[Веб-сервисы](/api_help/webservice/index.php)

[Классы](/api_help/webservice/classes/index.php)

[CXMLCreator](/api_help/webservice/classes/cxmlcreator/index.php)

createTagAttributed (доступен с 8.0.0)

createTagAttributed
===================

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
static
CXMLCreator
CXMLCreator::createTagAttributed(string heavyTag);Копировать
```

Статический метод возвращает созданный тэг **CXMLCreator** из названия
*heavyTag*,записанного в особенном формате. Если формат
*heavyTag* неверен, возвращается *true*.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *heavyTag* | Строка названия тэга в формате:  *[Индекс:]НазваниеТэга [Атрибут="Значение атрибута" ...]*  *Индекс* - число, помогающее поместить в ассоциативном массиве сразу несколько тегов с одинаковым названием.  *Атрибут* может быть записан в виде: *симв:симв = "Значение"* |

### Пример использования

```

CXMLCreator::createTagAttributed( "LicenseInfo xmlns=\"http://ws.strikeiron.com\"");
// Или
CXMLCreator::encodeValueLight( "LicenseInfo xmlns=\"http://ws.strikeiron.com\"",
	array(
		"1:ArrayOfStringEl" => "Строка1", 
		"2:ArrayOfStringEl" => "Строка2"
	)
);Копировать
```

Новинки документации в соцсетях:
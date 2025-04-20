[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearch](/api_help/search/classes/csearch/index.php)

SetOptions

SetOptions
==========

```
void CSearch::SetOptions(array arOptions)Копировать
```

Метод устанавливает дополнительные опции поиска.

  

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ERROR\_ON\_EMPTY\_STEM | Отвечает за настройку поиска с учетом морфологии.    Возможные значения:   * `true` — поиск выполнится только с учетом морфологии * `false` — сначала выполнится поиск с учетом морфологии. Если ничего не найдено — запустится поиск без учета морфологии    Значение по умолчанию — `true` |
| NO\_WORD\_LOGIC | Отключает обработку слов как логических операторов.    Возможные значения:   * `true` — отключить обработку * `false` — оставить обработку включенной    Значение по умолчанию — `false` |

  

#### Примеры кода

```
$obSearch = new CSearch;
$obSearch->SetOptions(
	array(
		"ERROR_ON_EMPTY_STEM" => false,
		"NO_WORD_LOGIC" => true,
	)
);Копировать
```

Новинки документации в соцсетях:
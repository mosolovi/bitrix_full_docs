[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearch](/api_help/search/classes/csearch/index.php)

Fetch (доступен с 4.0.0)

Fetch
=====

```
array
CSearch::Fetch(
);Копировать
```

Возвращает следующий найденный элемент. Нестатический метод.

Если поле результата URL начинается с символа "=", то вызываются обработчики события [OnSearchGetURL](/api_help/search/events/onsearchgeturl.php).

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

Смотри описание возвращаемого значения метода [CSearch::Search](/api_help/search/classes/csearch/search.php). Если достигнут конец выборки, возвращается false.

Новинки документации в соцсетях:
[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CFilterDictionary](/api_help/forum/developer/cfilterdictionary/index.php)

Add (доступен с 5.1.0)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CFilterDictionary::Add(
	array arFields 
);Копировать
```

Создает новый словарь с параметрами, указанными в массиве *arFields*. Возвращает код созданного словаря. Метод нестатический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в списке полей таблицы ["Словарь"](/api_help/forum/fields.php#cfilterdictionary). Обязательные поля должны быть заполнены. |  |

#### Возвращаемое значение

Возвращает код созданного словаря. В случае ошибки добавления возвращает False.

#### Смотрите также

* поля таблицы ["Словарь"](/api_help/forum/fields.php#cfilterdictionary).

### Примеры использования

```
<?
$arFields = Array(
	TITLE        - > $TITLE,
	TYPE      - > $TYPE,     
);
$ID = CFilterDictionary::Add($arFields);
if (IntVal($ID)<=0)
	echo "Error!";
?>Копировать
```

Новинки документации в соцсетях:
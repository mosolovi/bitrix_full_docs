[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

GetArrayByID (доступен с 6.5.0)

GetArrayByID
============

```
array
CIBlock::GetArrayByID(
	int ID,
	string FIELD = ""
);Копировать
```

Возвращает массив [полей](/api_help/iblock/fields.php#fiblock) информационного блока. Метод статический.

**Примечание**: если инфоблока с таким ID не существует, то метод вернет false.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор информационного блока |
| *FIELD* | Идентификатор поля. Если этот параметр задан, то метод вернет значение конкретного поля. |

#### Возвращаемое значение

Массив полей инфоблока.

#### Смотрите также

* [Поля инфоблока](/api_help/iblock/fields.php#fiblock)

#### Примеры использования

```
<?
echo CIBlock::GetArrayByID($IBLOCK_ID, "NAME");
?>Копировать
```

Новинки документации в соцсетях:
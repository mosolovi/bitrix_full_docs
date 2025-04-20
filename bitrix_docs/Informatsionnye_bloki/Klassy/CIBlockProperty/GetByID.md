[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)

GetByID (доступен с 3.0.3)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CIBlockProperty::GetByID(
	mixed ID,
	int IBLOCK_ID = false, 
	string IBLOCK_CODE = false
);Копировать
```

Возвращает свойство по его коду *ID*. Метод статический.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Числовой или символьный код свойства. |  |
| IBLOCK\_ID | Код информационного блока. Используется для уточнения свойства, если его *ID* задано символьным кодом и с таким символьным кодом свойства присутствует в нескольких информационных блоках. | 3.2.1 |
| IBLOCK\_CODE | Символьный код информационного блока. Используется для уточнения свойства, если его *ID* задано Символьным кодом и с таким символьным кодом свойства присутствует в нескольких информационных блоках. | 3.3.3 |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

**Примечание:** если заданы оба значения *IBLOCK\_ID* и *IBLOCK\_CODE*, то будет производиться попытка найти свойство в одном из них (логика "или").

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля свойства](/api_help/iblock/fields.php#fproperty)

### Примеры использования

```
<?
$res = CIBlockProperty::GetByID("SRC", false, "company_news");
if($ar_res = $res->GetNext())
	echo $ar_res['NAME'];
?>Копировать
```

Новинки документации в соцсетях:
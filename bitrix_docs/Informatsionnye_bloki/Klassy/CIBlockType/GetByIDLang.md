[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockType](/api_help/iblock/classes/ciblocktype/index.php)

GetByIDLang (доступен с 3.1.3)

GetByIDLang
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
mixed
CIBlockType::GetByIDLang(
	string ID,
	string LANGUAGE_ID,
	bool bFindAny = true
);Копировать
```

Метод возвращает языковые настройки типа информационных блоков по его коду *ID*, для языка *LANGUAGE\_ID*. Если для языка *LANGUAGE\_ID* нет настроек и параметр *bFindAny* установлен в true, метод вернет настройки типа для языка по умолчанию. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код типа. |
| LANGUAGE\_ID | Код языка. |
| bFindAny | Возвращать настройки для языка по умолчинию или нет. Необязательный. По умолчанию - возвращать. |

#### Возвращаемое значение

Если языковые настройки найдены, то метод возвратит массив [полей](/api_help/iblock/fields.php#fiblocktype) типа информационных блоков объединенный с массивом языкозависимых [параметров](/api_help/iblock/fields.php#fiblocktypelang) типа, в противном случае метод вернет false.

### Смотрите также

* [Поля CIBlockType](/api_help/iblock/fields.php#fiblocktype)
* [Языкозависимые поля CIBlockType](/api_help/iblock/fields.php#fiblocktypelang)

### Примеры использования

```
<?
$db_iblock_type = CIBlockType::GetList();
while($ar_iblock_type = $db_iblock_type->Fetch())
{
	if($arIBType = CIBlockType::GetByIDLang($ar_iblock_type["ID"], LANG))
	{
		echo htmlspecialcharsex($arIBType["NAME"])."<br>";
	}   
}
?>Копировать
```

Новинки документации в соцсетях:
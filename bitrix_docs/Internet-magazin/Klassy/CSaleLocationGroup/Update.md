[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocationGroup](/api_help/sale/classes/csalelocationgroup/index.php)

Update (доступен с 3.2.2, устарел с 15.0.0)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

Метод устарел. Рекомендуется использовать методы класса `\Bitrix\Sale\Location\GroupTable`.

### Описание и параметры

```
int
CSaleLocationGroup::Update( 
	int ID,
	array arFields
);Копировать
```

Метод обновляет параметры местоположения с кодом ID в соответствии с параметрами из массива arFields. Обновляются также страна и город этого местоположения. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код местоположения. |
| arFields | Ассоциативный массив параметров местоположения с ключами:  * **SORT** - индекс сортировки; * **COUNTRY\_ID** - код страны (если такая страна уже есть, иначе код должен быть нулем, и должен быть заполнен ключ COUNTRY); * **COUNTRY** - массив с параметрами страны (должен быть заполнен, если не установлен ключ COUNTRY\_ID или если ключ CHANGE\_COUNTRY установлен в значение Y); * **CHANGE\_COUNTRY** - флаг (Y/N), изменять ли параметры страны (долны быть установлены ключи COUNTRY\_ID и COUNTRY); * **WITHOUT\_CITY** - флаг (Y/N), означающий, что это местоположение без города (только страна) (если значением с этим ключем является N, то необходимо заполнить ключ CITY); * **CITY\_ID** - код города (если такой город уже есть, иначе код должен быть нулем, и должен быть заполнен ключ CITY); * **CITY** - массив с параметрами города (если установлен флаг WITHOUT\_CITY в значение Y, то этот ключ заполнять не нужно); * **LOCATION\_ID** - массив кодов местоположений, которые привязаны к данной группе местоположений.  Массив с параметрами страны должен содержать ключи:  * **NAME** - название страны (не зависящее от языка); * **SHORT\_NAME** - сокращенное название страны - абревиатура (не зависящее от языка); * **<код языка>** - ключем является код языка, а значением ассоциативный массив вида    ```   array(   	"LID" => "код языка",   	"NAME" => "название страны на этом языке",   	"SHORT_NAME" => "сокращенное название страны (аббревиатура) на этом языке"   )Копировать   ```    Эта пара ключ-значение должна присутствовать для каждого языка системы.  Массив с параметрами города должен содержать ключи:  * **NAME** - название города (не зависящее от языка); * **SHORT\_NAME** - сокращенное название города - аббревиатура (не зависящее от языка); * **<код языка>** - ключем является код языка, а значением ассоциативный массив вида    ```   array(   	"LID" => "код языка",   	"NAME" => "название города на этом языке",   	"SHORT_NAME" => "сокращенное название города (аббревиатура) на этом языке"   )Копировать   ```    Эта пара ключ-значение должна присутствовать для каждого языка системы. |

#### Возвращаемые значения

Возвращается код измененного местоположения или *false* у случае ошибки.

### Примеры использования

```
<?
$arFields = array(
	"SORT" => 100,
	"COUNTRY_ID" => 8,
	"WITHOUT_CITY" => "N"
);
 
$arCity = array(
	"NAME" => "Kaliningrad",
	"SHORT_NAME" => "Kaliningrad",
	"ru" => array(
		"LID" => "ru",
		"NAME" => "Калининград",
		"SHORT_NAME" => "Калининград"
	),
	"en" => array(
		"LID" => "en",
		"NAME" => "Kaliningrad",
		"SHORT_NAME" => "Kaliningrad"
	)
);
 
$arFields["CITY"] = $arCity;
 
if (!CSaleLocation::Update(6, $arFields))
	echo "Ошибка изменения местоположения";
?>Копировать
```

```
function CreateCityRussia($arFields, $regionName, &$strError) 
{
	// Ищем группу местоположений, к которой необходимо привязать местоположение
	$locGroupID = 0;
	$resLocationGroup = CSaleLocationGroup::GetList(array("ID"=>"ASC"), array());
	while($arLocationGroup = $resLocationGroup->Fetch()) 
	{
		if(mb_strtolower($arLocationGroup["NAME"], "Windows-1251") == mb_strtolower($regionName, "Windows-1251")) $locGroupID = $arLocationGroup["ID"];
	}
   
	// Если группа найдена, определяем список привязанных к ней местоположений и добавляем к списку новое
	if($locGroupID) 
	{
		// Создаем новый город в стране Россия и новое местоположение
		$arCoutry = CSaleLocation::GetList(array(), array("LID" => LANGUAGE_ID, "CITY_NAME" => false, "COUNTRY_NAME" => "Россия"))->Fetch();
		$cityId = CSaleLocation::AddCity($arFields);
		$ID = CSaleLocation::AddLocation(array("COUNTRY_ID" => $arCoutry['COUNTRY_ID'], "CITY_ID" => $cityId));
     
		// Формируем новый список местоположений группы
		$resLocGroup = CSaleLocationGroup::GetLocationList(array("LOCATION_GROUP_ID" => $locGroupID));
		$locList = array();
		while($arLocGroup = $resLocGroup->Fetch()) 
		{
			$locList[] = $arLocGroup["LOCATION_ID"];
		}
		$locList[] = $ID;
     
		// Записываем новый список местоположений группы
		$arFields = CSaleLocationGroup::GetByID($locGroupID);
		$arFields["LOCATION_ID"] = $locList;
		if (!CSaleLocationGroup::Update($locGroupID, $arFields))
			$strError = "Ошибка добавления местоположения к группе местоположений";
		return $ID;
	} 
	else 
	{
		// В противном случае записываем сообщение об ошибке
		$strError = "Ошибка создания местоположения: Не найдена группа местоположений $regionName";
		return false; 
	}
}Копировать
```

Новинки документации в соцсетях:
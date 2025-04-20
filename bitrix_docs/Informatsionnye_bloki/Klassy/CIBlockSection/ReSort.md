[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)

ReSort (доступен с 3.0.4)

ReSort
======

```
CIBlockSection::ReSort(
	int IBLOCK_ID
);Копировать
```

Метод пересчитывает параметры левой и правой границ для всех разделов информационного блока *IBLOCK\_ID*. Должен использоваться после применения серии добавлений или изменений разделов при помощи методов [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)::[Add](/api_help/iblock/classes/ciblocksection/add.php)() или [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)::[Update](/api_help/iblock/classes/ciblocksection/update.php)() c отключенным параметром *bReSort*, в целях повышения производительности. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| IBLOCK\_ID | код информационного блока. |

#### Смотрите также

- [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)::[Add](/api_help/iblock/classes/ciblocksection/add.php)()
- [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)::[Update](/api_help/iblock/classes/ciblocksection/update.php)()

  #### Примеры использования

  ```
  <?
  $obSect = new CIBlockSection;
  for($i=0; $i<100; $i++)
  {
  	$obSect->Add(Array('NAME'=>'Section #'.$i, 'IBLOCK_ID'=>$IBLOCK_ID), false);
  }
  CIBlockSection::ReSort($IBLOCK_ID);
  ?>Копировать
  ```

Новинки документации в соцсетях:
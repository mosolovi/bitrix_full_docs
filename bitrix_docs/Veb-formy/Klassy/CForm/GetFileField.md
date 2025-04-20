[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetFileField (3.1.1)

GetFileField
============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetFileField(
	int answer_id,
	mixed width = "",
	string file_type = "IMAGE",
	int max_file_size = 0,
	mixed file_id = "",
	string add_to_file = "class=\"inputfile\"",
	string add_to_checkbox = "class=\"inputcheckbox\"",
)Копировать
```

Возвращает HTML код поля для загрузки файла. Данное поле предназначено для ввода [ответа](/api_help/form/terms.php#answer) типа "**image**" или "**file**".

Метод может использоваться как в форме
создания нового [результата](/api_help/form/terms.php#result), так и в форме редактирования существующего. Метод нестатический.

**Примечание**  
Имя результирующего HTML поля будет сформировано по следующей маске:  
 **form\_***file\_type***\_***answer\_id*

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *answer\_id* | ID [ответа](/api_help/form/terms.php#answer). |  |
| *width* | Ширина результирующего поля для ввода файла:  `<input type="file" size="width" ...>`   Параметр необязательный. По умолчанию - "". |  |
| *file\_type* | Тип файла, допустимы следующие значения:  * **IMAGE** - изображение; * **FILE** - произвольный файл.  Параметр необязательный. По умолчанию - "IMAGE" (изображение). |  |
| *max\_file\_size* | Максимальный размер загружаемого файла (в байтах).  Параметр необязательный. По умолчанию - 0 (без ограничений). |  |
| *file\_id* | ID загруженного (редактируемого) файла.  Параметр необязательный. По умолчанию - "". |  |
| *add\_to\_file* | Произвольный HTML, который будет добавлен в HTML тег поля для загрузки файла:  `<input type="file" add_to_file ...>`   Параметр необязательный. По умолчанию - "class=\"inputfile\"". | 3.3.10 |
| *add\_to\_checkbox* | Произвольный HTML, который будет добавлен в HTML тег флага удаления редактируемого файла:  `<input type="checkbox" add_to_checkbox ...>`   Параметр необязательный. По умолчанию - "class=\"inputcheckbox\"". | 3.3.10 |
| *PARAM\_TEXT* | Необязательный параметр. Удален с версии 4.0.4 | 3.3.10 |

### Смотрите также

* [Имена HTML полей](/api_help/form/htmlnames.php)

### Примеры использования

```
<?
/*******************************************
       Редактирование результата
*******************************************/
$RESULT_ID = 12; // ID результата
?>
<form action="" method="POST">
<table>
	<tr>
		<td>Фотография:</td>
		<td><?
			/************************************************************
                                    Изображение
			************************************************************/
			 // массив описывающий поле ответа
			// содержит минимально-необходимые поля
			$arAnswer = array(
				"ID"            => 607,   // ID поля для ответа на вопрос "Фотография"
				"FIELD_WIDTH"   => 10,    // ширина поля
				"FIELD_PARAM"   => ""     // параметры поля
			);
			// попробуем получить параметры загруженного файла
			if ($arFile = CFormResult::GetFileByAnswerID($RESULT_ID, $arAnswer["ID"])):
				// если файл был получен то
				if (intval($arFile["USER_FILE_ID"])>0):
					// если это изображение то
					if ($arFile["USER_FILE_IS_IMAGE"]=="Y") :
						// выведем изображение
						echo CFile::ShowImage(
							$arFile["USER_FILE_ID"], 
							0, 
							0, 
							"border=0", 
							"", 
							true
						);
					endif;
					echo "<br><br>"; 
				endif;
			endif;
			// выведем поле для ввода файла
			echo CForm::GetFileField(
				$arAnswer["ID"],
				$arAnswer["FIELD_WIDTH"],
				"IMAGE",
				0,  // максимальный размер файла не ограничен
				$arFile["USER_FILE_ID"],
				$arAnswer["FIELD_PARAM"]);
		?></td>
	</tr>
	<tr>
		<td>Резюме:</td>
		<td><?
			/************************************************************
                                Произвольный файл
			************************************************************/
			// массив описывающий поле ответа
			// содержит минимально-необходимые поля
			$arAnswer = array(
				"ID"            => 610,   // ID поля для ответа на вопрос "Резюме"
				"FIELD_WIDTH"   => 10,    // ширина поля
				"FIELD_PARAM"   => ""     // параметры поля
			);
			// попробуем получить параметры загруженного файла
			if ($arFile = CFormResult::GetFileByAnswerID($RESULT_ID, $arAnswer["ID"])):
				// если файл был получен то
				if (intval($arFile["USER_FILE_ID"])>0):
					// выведем информацию о файле
					?>
                    
					<a title="Просмотр файла" target="_blank" class="tablebodylink" href="/bitrix/tools/form_show_file.php?rid=<?=$result_id?>&hash=<?echo $arFile["USER_FILE_HASH"]?>〈=<?=LANGUAGE_ID?>"><?=htmlspecialchars($arFile["USER_FILE_NAME"])?></a>
					&nbsp;
					(<?
					$a = array("b", "Kb", "Mb", "Gb");
					$pos = 0;
					$size = $arFile["USER_FILE_SIZE"];
					while($size>=1024) {$size /= 1024; $pos++;}
					echo round($size,2)." ".$a[$pos];
					?>)
					&nbsp;&nbsp;
					[&nbsp;<a title="<?echo str_replace("#FILE_NAME#", $arFile["USER_FILE_NAME"], "Скачать")?>" class="tablebodylink" href="/bitrix/tools/form_show_file.php?rid=<?=$result_id?>&hash=<?echo $arFile["USER_FILE_HASH"]?>〈=<?=LANGUAGE_ID?>&action=download">Скачать</a>&nbsp;]
					<br><br>
                    
					<?
				endif;
			endif;
			// выведем поле для ввода файла
			echo CForm::GetFileField(
				$arAnswer["ID"],
				$arAnswer["FIELD_WIDTH"],
				"FILE",
				0,  // максимальный размер файла не ограничен
				$arFile["USER_FILE_ID"],
				$arAnswer["FIELD_PARAM"]);
		?></td>
	</tr>
</table>
<input type="submit" name="save" value="Сохранить">
</form>Копировать
```

Новинки документации в соцсетях:
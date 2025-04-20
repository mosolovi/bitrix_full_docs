[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

SetField (3.3.10)

SetField
========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CFormResult::SetField(
	int result_id,
	string field_sid,
	mixed value = false
)Копировать
```

Для указанного [результата](/api_help/form/terms.php#result) обновляет
значения [ответа](/api_help/form/terms.php#answer) на [вопрос](/api_help/form/terms.php#question) или обновляет значение [поля](/api_help/form/terms.php#field). Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *result\_id* | ID [результата](/api_help/form/terms.php#result). |  |
| *field\_varname* |  | Удален с 4.0.4 |
| *field\_sid* | Символьный идентификатор [вопроса](/api_help/form/terms.php#question) или [поля](/api_help/form/terms.php#field). | 4.0.4 |
| *value* | Значение, которое необходимо сохранить. В зависимости от типа обновляемого поля, данный параметр имеет различный формат.  * При обновлении значения [поля](/api_help/form/terms.php#field), в данном параметре   достаточно указать новое значение обновляемого [поля](/api_help/form/terms.php#field). * При обновлении значений [ответов](/api_help/form/terms.php#answer) на [вопрос](/api_help/form/terms.php#question), формат данного   параметра следующий:    ```   array (   	ID ответа 1 => значение ответа 1,   	ID ответа 2 => значение ответа 2,   	...   )Копировать   ```    Если [ответ](/api_help/form/terms.php#answer) принадлежит   к одним из следующих типов:   + **radio** - переключатель одиночного выбора (radio-кнопка);   + **checkbox** - флаг множественного выбора (checkbox);   + **dropdown** - элемент выпадающего списка одиночного выбора;   + **multiselect** - элемент списка множественного выбора,то в качестве "*значения ответа*" достаточно указать ""   (пустое значение).   Если [ответ](/api_help/form/terms.php#answer) имеет один из следующих   типов:   + **text** - однострочное текстовое поле;   + **textarea** - многострочное текстовое поле;   + **date** - поле для ввода даты;   + **password** - поле для ввода пароля,то в качестве   "*значения ответа*" необходимо указать значение, которое могло бы   быть введено с клавиатуры при ответе на данный [вопрос](/api_help/form/terms.php#question).   Если [ответ](/api_help/form/terms.php#answer) имеет один из следующих   типов:   + **image** - поле для загрузки изображения;   + **file** - поле для загрузки произвольного файла.то в   качестве "*значения ответа*" необходимо указать массив, описывающий   файл и имеющий следующий ключи:   + **name** - имя файла;   + **size** - размер файла;   + **tmp\_name** - временный путь на сервере;   + **type** - тип загружаемого файла.Такой массив можно   получить с помощью функции [CFile::MakeFileArray](/api_help/main/reference/cfile/makefilearray.php).  Параметр *value* необязательный. С версии 4.0.4 значение по умолчанию - "false" (значение [поля](/api_help/form/terms.php#field) или значение [ответа](/api_help/form/terms.php#answer) на [вопрос](/api_help/form/terms.php#question) будут просто удалены). |  |

### Смотрите также

* [CFormResult::Update](/api_help/form/classes/cformresult/update.php)
* [CFile::MakeFileArray](/api_help/main/reference/cfile/makefilearray.php)

### Примеры использования

```
$RESULT_ID = 186;
/**************************************************************
            Обновление значений ответов на вопросы
**************************************************************/
// обновим ответ на вопрос "Фамилия, имя, отчество"
$arVALUE = array();
$FIELD_SID = "VS_NAME"; // символьный идентификатор вопроса
$ANSWER_ID = 586; // ID поля ответа
$arVALUE[$ANSWER_ID] = "Иванов Иван";
CFormResult::SetField($RESULT_ID, $FIELD_SID, $arVALUE);
// обновим ответ на вопрос "Дата рождения"
$arVALUE = array();
$FIELD_SID = "VS_BIRTHDAY"; // символьный идентификатор вопроса
$ANSWER_ID = 587; // ID поля ответа
$arVALUE[$ANSWER_ID] = "18.06.1975";
CFormResult::SetField($RESULT_ID, $FIELD_SID, $arVALUE);
// обновим ответ на вопрос "Какие области знаний вас интересуют?"
$arVALUE = array();
$FIELD_SID = "VS_INTEREST"; // символьный идентификатор вопроса
$arVALUE[612] = ""; // ID поля ответа "математика"
$arVALUE[613] = ""; // ID поля ответа "физика"
$arVALUE[614] = ""; // ID поля ответа "история"
CFormResult::SetField($RESULT_ID, $FIELD_SID, $arVALUE);
// обновим ответ на вопрос "Фотография"
$arVALUE = array();
$FIELD_SID = "VS_PHOTO"; // символьный идентификатор вопроса
$ANSWER_ID = 607; // ID поля ответа
$path = $_SERVER["DOCUMENT_ROOT"]."/images/news.gif"; // путь к файлу
$arVALUE[$ANSWER_ID] = CFile::MakeFileArray($path);
CFormResult::SetField($RESULT_ID, $FIELD_SID, $arVALUE);
// обновим ответ на вопрос "Резюме"
$arVALUE = array();
$FIELD_SID = "VS_RESUME"; // символьный идентификатор вопроса
$ANSWER_ID = 610; // ID поля ответа
$path = $_SERVER["DOCUMENT_ROOT"]."/docs/alawarauthorarea.doc"; // путь к файлу
$arVALUE[$ANSWER_ID] = CFile::MakeFileArray($path);
CFormResult::SetField($RESULT_ID, $FIELD_SID, $arVALUE);
/**************************************************************
                Обновление значений полей
**************************************************************/
// обновим значение поля "Рассчитанная стоимость"
$FIELD_SID = "VS_PRICE"; // символьный идентификатор вопроса
$VALUE = "155";
CFormResult::SetField($RESULT_ID, $FIELD_SID, $VALUE);
?>Копировать
```

Новинки документации в соцсетях:
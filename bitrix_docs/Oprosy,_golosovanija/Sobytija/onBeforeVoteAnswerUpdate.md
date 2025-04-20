[Опросы, голосования](/api_help/vote/index.php)

[События](/api_help/vote/vote_events/index.php)

onBeforeVoteAnswerUpdate (с версии 8.5.0)

onBeforeVoteAnswerUpdate
========================

Событие вызывается в методе \CVoteAnswer::Update перед изменением ответа.

#### Пример использования

  

Например, у нас есть группа
опросов



![futboll.png](/upload/medialibrary/cc4/futboll.png "futboll.png")
по спортивной тематике.

  

```
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("vote", "onBeforeVoteAnswerUpdate", ["MyClassForVote", "onBeforeVoteAnswerUpdateHandler"]);
class MyClassForVote
{
	public static function onBeforeVoteAnswerUpdateHandler($id, &$fields)
	{
		// Аргумент $fields передан по ссылке, т.е. изменяя данные $fields, вы влияете на сохранённые данные.
		$channel = getChannelByQuestionId($fields["QUESTION_ID"]); // ф-ция, возвращающая массив CHANNEL
		if (
			$channel["ID"] == 6 // Например, для опросов группы (с номером 6) по спортивной тематике
			&&
			empty($fields["IMAGE_ID"]) // и пустой картинкой
		)
		{
			// будем Возвращать ошибку загрузки
			global $APPLICATION;
			$APPLICATION->throwException("Ай-ай-ай! Нехорошо писать ответы в этой группе без картинки. ");
			return false;
		}
	}
}Копировать
```

Новинки документации в соцсетях:
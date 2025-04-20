[Опросы, голосования](/api_help/vote/index.php)

[События](/api_help/vote/vote_events/index.php)

onBeforeVoteUpdate (с версии 8.5.0)

onBeforeVoteUpdate
==================

Событие вызывается в методе \Bitrix\Vote\VoteTable::onBeforeUpdate перед обновлением опроса.

#### Пример использования

  

Например, у нас есть группа
опросов



![futboll.png](/upload/medialibrary/cc4/futboll.png "futboll.png")
по спортивной тематике.

  

```
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("vote", "onBeforeVoteUpdate", ["MyClassForVote", "onBeforeVoteUpdateHandler"]);
class MyClassForVote
{
	public static function onBeforeVoteUpdateHandler($id, &$fields)
	{
		// Аргумент $fields передан по ссылке, т.е. изменяя данные $fields, вы влияете на сохранённые данные.
		if (
			$fields["CHANNEL_ID"] == 5 // Например, для опросов группы (с номером 5) по спортивной тематике
			&&
			empty($fields["IMAGE_ID"]) // и пустой картинкой
		)
		{
			// будем подставлять картинку мяча, например
			$fields["IMAGE_ID"] = [
				"name" => "ball.png",
				"type" => "image/png",
				"tmp_name" => __DIR__."/soccer-ball.png",
				"size" => 20008,
				"error" => 0
			];
		}
	}
}Копировать
```

Новинки документации в соцсетях:
[Блоги](/api_help/blogs/index.php)

[События](/api_help/blogs/events/index.php)

События модуля блогов

События модуля блогов
=====================

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnBeforeBlogAdd](/api_help/blogs/events/onbeforeblogadd.php) | перед добавлением блога. | [CBlog::Add](/api_help/blogs/classes/cblog/add.php) | 5.0.2 |
| [OnBlogAdd](/api_help/blogs/events/onblogadd.php) | при добавлении блога. | [CBlog::Add](/api_help/blogs/classes/cblog/add.php) | 5.0.2 |
| [OnBeforeBlogUpdate](/api_help/blogs/events/onbeforeblogupdate.php) | перед изменением блога. | [CBlog::Update](/api_help/blogs/classes/cblog/update.php) | 5.0.2 |
| [OnBlogUpdate](/api_help/blogs/events/onblogupdate.php) | при изменении блога. | [CBlog::Update](/api_help/blogs/classes/cblog/update.php) | 5.0.2 |
| [OnBeforeBlogDelete](/api_help/blogs/events/onbeforeblogdelete.php) | перед удалением блога. | [CBlog::Delete](/api_help/blogs/classes/cblog/delete.php) | 5.0.1 |
| [OnBlogDelete](/api_help/blogs/events/onblogdelete.php) | при удалении блога. | [CBlog::Delete](/api_help/blogs/classes/cblog/delete.php) | 5.0.1 |
| OnBeforeCommentAdd | перед добавлением комментария. | [CBlogComment::Add](/api_help/blogs/classes/cblogcomment/add.php) | 9.5.0 |
| OnBeforeCommentDelete | перед удалением комментария. Текст ошибки, зарегистрированной в обработчике этого события, отображается в интерфейсе живой ленты. | [CBlogComment::Delete](/api_help/blogs/classes/cblogcomment/delete.php) | 9.5.0 |
| OnBeforeCommentUpdate | перед изменением комментария. | [CBlogComment::Update](/api_help/blogs/classes/cblogcomment/update.php) | 9.5.0 |
| OnBeforePostAdd | перед добавлением сообщения. | [CBlogPost::Add](/api_help/blogs/classes/cblogpost/add.php) | 9.5.0 |
| OnBeforePostDelete | перед удалением сообщения. | [CBlogPost::Delete](/api_help/blogs/classes/cblogpost/delete.php) | 9.5.0 |
| OnBeforePostUpdate | перед изменением сообщения. | [CBlogPost::Update](/api_help/blogs/classes/cblogpost/update.php) | 9.5.0 |
| OnCommentAdd | при добавлении комментария. | [CBlogComment::Add](/api_help/blogs/classes/cblogcomment/add.php) | 9.5.0 |
| OnCommentDelete | при удалении комментария. | [CBlogComment::Delete](/api_help/blogs/classes/cblogcomment/delete.php) | 9.5.0 |
| OnCommentUpdate | при изменении комментария. | [CBlogComment::Update](/api_help/blogs/classes/cblogcomment/update.php) | 9.5.0 |
| OnPostAdd | при добавлении сообщения. | [CBlogPost::Add](/api_help/blogs/classes/cblogpost/add.php) | 9.5.0 |
| OnPostDelete | при удалении сообщения. | [CBlogPost::Delete](/api_help/blogs/classes/cblogpost/delete.php) | 9.5.0 |
| OnPostUpdate | при изменении сообщения. | [CBlogPost::Update](/api_help/blogs/classes/cblogpost/update.php) | 9.5.0 |
| videoConvert | при конвертации видео. | blogTextParser::blogConvertVideo | 9.0.0 |
| BlogImageSize | при конвертировании тега типа  ``` [IMG ID=12345]Копировать ```  в строку типа *<img .../>* | [blogTextParser::blogTextParser](/api_help/blogs/classes/blogtextparser/index.php) |  |
| OnBeforePostUserFieldUpdate | после изменения\добавления сообщения в блог, но перед обновлением пользовательских свойств. | [CBlogPost::Update](/api_help/blogs/classes/cblogpost/update.php) |  |
| OnBlogPostMentionNotifyIm | после отправки уведомления об упоминании в сообщении\комментарии. | CBlogPost::NotifyIm |  |

Новинки документации в соцсетях:
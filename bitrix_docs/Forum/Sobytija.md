[Форум](/api_help/forum/index.php)

[События](/api_help/forum/events/index.php)

События модуля Форум (доступно с 3.3.3)

События модуля Форум
====================

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| GetAuditTypesForum |  | CEventForum::GetAuditTypes | 11.0.0 |
| OnAfterForumDelete | после удаления форума. | [CForumNew::Delete](/api_help/forum/developer/cforumnew/delete.php) |  |
| onAfterForumAdd | после добавления форума. | [CForumNew::Add](/api_help/forum/developer/cforumnew/add.php) |  |
| onAfterForumUpdate | после редактирования форума. | [CForumNew::Update](/api_help/forum/developer/cforumnew/update.php) |  |
| onAfterGroupForumsAdd | после добавления группы форума. | [CForumGroup::Add](/api_help/forum/developer/cforumgroup/add.php) |  |
| onAfterGroupForumsUpdate | после редактирования группы форума. | [CForumGroup::Update](/api_help/forum/developer/cforumgroup/update.php) |  |
| onAfterMessageAdd | после добавления сообщения форума. | [CForumMessage::Add](/api_help/forum/developer/cforummessage/add.php) |  |
| onAfterMessageDelete | после удаления сообщения форума. | [CForumMessage::Delete](/api_help/forum/developer/cforummessage/delete.php) |  |
| onAfterMessageUpdate | после редактирования сообщения форума. | [CForumMessage::Update](/api_help/forum/developer/cforummessage/update.php) |  |
| onAfterPMCopy | после копирования персонального сообщения. | CForumPrivateMessage::Copy | 11.5.1 |
| onAfterPMSend | после отправки персонального сообщения. | CForumPrivateMessage::Send | 11.5.1 |
| onAfterTopicAdd | после добавления темы форума. | [CForumTopic::Add](/api_help/forum/developer/cforumtopic/add.php) |  |
| onAfterTopicDelete | после удаления темы форума. | [CForumTopic::Delete](/api_help/forum/developer/cforumtopic/delete.php) |  |
| onAfterTopicUpdate | после редактирования темы форума. | [CForumTopic::Update](/api_help/forum/developer/cforumtopic/update.php) |  |
| onAfterUserAdd | после добавления пользователя форума. | [CForumUser::Add](/api_help/forum/developer/cforumuser/add.php) |  |
| onAfterUserDelete | после удаления пользователя форума. | [CForumUser::Delete](/api_help/forum/developer/cforumuser/delete.php) |  |
| onAfterUserUpdate | после редактирования пользователя форума. | [CForumUser::Update](/api_help/forum/developer/cforumuser/update.php) |  |
| onBeforeForumAdd | перед добавлением форума. | [CForumNew::Add](/api_help/forum/developer/cforumnew/add.php) |  |
| OnBeforeForumDelete | перед удалением форума. | [CForumNew::Delete](/api_help/forum/developer/cforumnew/delete.php) |  |
| onBeforeForumUpdate | перед редактированием форума. | [CForumNew::Update](/api_help/forum/developer/cforumnew/update.php) |  |
| onBeforeGroupForumsAdd | перед созданием группы форумов. | [CForumGroup::Add](/api_help/forum/developer/cforumgroup/add.php) |  |
| onBeforeGroupForumsUpdate | перед редактированием группы форумов. | [CForumGroup::Update](/api_help/forum/developer/cforumgroup/update.php) |  |
| onBeforeMailMessageSend | перед отправкой сообщения на почту. | CForumMessage::SendMailMessage | 12.5.1 |
| onBeforeMessageAdd | перед добавлением сообщения форума. | [CForumMessage::Add](/api_help/forum/developer/cforummessage/add.php) |  |
| onBeforeMessageDelete | перед удалением сообщения форума. | [CForumMessage::Delete](/api_help/forum/developer/cforummessage/delete.php) |  |
| onBeforeMessageUpdate | перед редактированием сообщения форума. | [CForumMessage::Update](/api_help/forum/developer/cforummessage/update.php) | 11.5.1 |
| onBeforePMCopy | перед копированием персонального сообщения. | CForumPrivateMessage::Copy | 11.5.1 |
| onBeforePMDelete | перед удалением персонального сообщения. | [CForumPrivateMessage::Delete](/api_help/forum/developer/cforumprivatemessage/delete.php) | 11.5.1 |
| onBeforePMMakeRead | перед чтением персонального сообщения. | CForumPrivateMessage::MakeRead | 11.5.1 |
| onBeforePMSend | перед отправкой персонального сообщения. | [CForumPrivateMessage::Send](/api_help/forum/developer/cforumprivatemessage/send.php) | 11.5.1 |
| onBeforePMUpdate | перед редактированием персонального сообщения. | [CForumPrivateMessage::Update](/api_help/forum/developer/cforumprivatemessage/update.php) | 11.5.1 |
| onBeforeTopicAdd | перед добавлением темы форума. | [CForumTopic::Add](/api_help/forum/developer/cforumtopic/add.php) |  |
| onBeforeTopicDelete | перед удалением темы форума. | [CForumTopic::Delete](/api_help/forum/developer/cforumtopic/delete.php) |  |
| onBeforeTopicUpdate | перед редактированием темы форума. | [CForumTopic::Update](/api_help/forum/developer/cforumtopic/update.php) |  |
| onBeforeUserAdd | перед добавлением пользователя форума. | [CForumUser::Add](/api_help/forum/developer/cforumuser/add.php) |  |
| onBeforeUserDelete | перед удалением пользователя форума. | [CForumUser::Delete](/api_help/forum/developer/cforumuser/delete.php) |  |
| onBeforeUserUpdate | перед редактированием пользователя форума. | [CForumUser::Update](/api_help/forum/developer/cforumuser/update.php) |  |
| OnForumDelete | при удалении форума. | [CForumNew::Delete](/api_help/forum/developer/cforumnew/delete.php) |  |
| onMessageModerate | при модерировании сообщения форума. | ForumModerateMessage | 12.0.2 |

Новинки документации в соцсетях:
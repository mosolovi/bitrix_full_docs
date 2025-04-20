[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

Список событий

Список событий
==============

Включить вкладки

Выполнение страницы

Пользователи и авторизация

Группы пользователей

Файлы и права

Шаблоны почтовых сообщений

Сайты

Языки

Панель управления и админ. часть

Рейтинги

Парсинг текста

Обновление системы

Установка модулей

Пользовательские поля

Прочие события

Ниже представлены списки событий главного модуля. Для регистрации обработчика укажите в качестве идентификатора модуля - "main".

### Выполнение страницы

События, вызывающиеся в процессе выполнения страницы:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnPageStart](/api_help/main/events/onpagestart.php) | в начале выполняемой части пролога сайта, после подключения всех библиотек и отработки [агентов](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3436). |  | 3.0.6 |
| [OnBeforeProlog](/api_help/main/events/onbeforeprolog.php) | в выполняемой части пролога сайта (после события [OnPageStart](/api_help/main/events/onpagestart.php)). |  | 3.0.6 |
| [OnProlog](/api_help/main/events/onprolog.php) | в начале визуальной части пролога сайта. | CAllMain::PrologActions | 4.0.14 |
| [OnEpilog](/api_help/main/events/onepilog.php) | в конце визуальной части эпилога сайта. |  | 3.3.21 |
| [OnAfterEpilog](/api_help/main/events/onafterepilog.php) | в конце выполняемой части эпилога сайта (после события [OnEpilog](/api_help/main/events/onepilog.php)). |  | 3.0.11 |
| OnBeforeEndBufferContent | перед выводом буферизированного контента | CAllMain::EndBufferContent | 9.5.0 |
| OnBeforeRestartBuffer | перед сбросом буфера контента | CAllMain::RestartBuffer | 6.5.4 |
| [OnEndBufferContent](/api_help/main/events/onendbuffercontent.php) | при выводе буферизированного контента. | CAllMain::EndBufferContent | 7.0.1 |

#### Смотрите также

* [Этапы выполнения страницы](/api_help/main/general/pageplan.php)

### Пользователи и авторизация

События при работе с пользователями и авторизация:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnBeforeUserRegister](/api_help/main/events/onbeforeuserregister.php) | до попытки зарегистрировать нового пользователя | [CUser::Register](/api_help/main/reference/cuser/register.php) | 4.0.6 |
| [OnAfterUserRegister](/api_help/main/events/onafteruserregister.php) | после попытки регистрации нового пользователя | [CUser::Register](/api_help/main/reference/cuser/register.php) | 4.0.6 |
| [OnBeforeUserSimpleRegister](/api_help/main/events/onbeforeusersimpleregister.php) | до попытки упрощённой регистрации нового пользователя | [CUser::SimpleRegister](/api_help/main/reference/cuser/simpleregister.php) | 4.0.6 |
| [OnAfterUserSimpleRegister](/api_help/main/events/onafterusersimpleregister.php) | после попытки упрощённой регистрации нового пользователя | [CUser::SimpleRegister](/api_help/main/reference/cuser/simpleregister.php) | 4.0.6 |
| [OnBeforeUserLogin](/api_help/main/events/onbeforeuserlogin.php) | до попытки авторизации пользователя | [CUser::Login](/api_help/main/reference/cuser/login.php) | 4.0.6 |
| [OnUserLoginExternal](/api_help/main/events/onuserloginexternal.php) | перед попыткой авторизации пользователя, предназначен для проверки [внешней авторизации](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3574). | [CUser::Login](/api_help/main/reference/cuser/login.php) | 4.0.6 |
| [OnAfterUserLogin](/api_help/main/events/onafteruserlogin.php) | после попытки авторизации пользователя | [CUser::Login](/api_help/main/reference/cuser/login.php) | 4.0.6 |
| [OnBeforeUserLoginByHash](/api_help/main/events/onbeforeuserloginbyhash.php) | перед попыткой авторизации пользователя | [CUser::LoginByHash](/api_help/main/reference/cuser/loginbyhash.php) | 4.0.6 |
| [OnAfterUserLoginByHash](/api_help/main/events/onafteruserloginbyhash.php) | после попытки авторизации пользователя | [CUser::LoginByHash](/api_help/main/reference/cuser/loginbyhash.php) | 4.0.6 |
| [OnAfterUserAuthorize](/api_help/main/events/onafteruserauthorize.php) | после [авторизации](/api_help/main/reference/cuser/authorize.php) пользователя | CAllUser::Authorize | 4.0.6 |
| [OnBeforeUserLogout](/api_help/main/events/onbeforeuserlogout.php) | перед завершением сеанса авторизации пользователя | [CUser::Logout](/api_help/main/reference/cuser/logout.php) | 4.0.6 |
| [OnAfterUserLogout](/api_help/main/events/onafteruserlogout.php) | после завершения сеанса авторизации пользователя | [CUser::Logout](/api_help/main/reference/cuser/logout.php) | 4.0.6 |
| [OnBeforeUserAdd](/api_help/main/events/onbeforeuseradd.php) | перед добавлением нового пользователя. | CAllUser::CheckFields | 4.0.16 |
| [OnAfterUserAdd](/api_help/main/events/onafteruseradd.php) | после добавления нового пользователя. | [CUser::Add](/api_help/main/reference/cuser/add.php) | 4.0.16 |
| [OnBeforeUserUpdate](/api_help/main/events/onbeforeuserupdate.php) | перед изменением параметров пользователя. | CAllUser::CheckFields | 4.0.16 |
| [OnAfterUserUpdate](/api_help/main/events/onafteruserupdate.php) | после изменения параметров пользователя. | CAllUser::Update | 4.0.16 |
| [OnBeforeUserDelete](/api_help/main/events/onbeforeuserdelete.php) | перед удалением пользователя. | CAllUser::Delete | 3.0.10 |
| [OnUserDelete](/api_help/main/events/onuserdelete.php) | во время удаления пользователя. | CAllUser::Delete | 3.0.10 |
| [OnExternalAuthList](/api_help/main/events/onexternalauthlist.php) | для получения списка источников внешней авторизации. | CAllUser::GetExternalAuthList | 4.0.6 |
| OnBeforeUserChangePassword | перед сменой пользовательского пароля | [CUser::ChangePassword](/api_help/main/reference/cuser/changepassword.php) | 4.0.14 |
| OnBeforeUserSendPassword | перед отправкой пользователю пароля | [CUser::SendPassword](/api_help/main/reference/cuser/sendpassword.php) | 4.0.14 |
| OnUserLogin | при попытке авторизации | [CUser::Authorize](/api_help/main/reference/cuser/authorize.php) | 3.3.0 |
| OnUserLogout | после завершения сеанса авторизации пользователя | [CUser::Logout](/api_help/main/reference/cuser/logout.php) | 3.3.13 |
| [OnSendUserInfo](/api_help/main/events/onsenduserinfo.php) | при передаче данных о пользователе | [CUser::SendUserInfo](/api_help/main/reference/cuser/senduserinfo.php) | 4.0.6 |
| OnAuthProvidersBuildList | при создании провайдеров авторизации | CAccess::\_\_construct | 11.0.7 |

#### Смотрите также

* [Внешняя авторизация](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3574)

### Группы пользователей

События при работе с группами пользователей:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnBeforeGroupDelete](/api_help/main/events/onbeforegroupdelete.php) | перед [удалением группы](/api_help/main/reference/cgroup/delete.php) пользователей | CAllGroup::Delete | 3.0.10 |
| [OnGroupDelete](/api_help/main/events/ongroupdelete.php) | при [удалении группы](/api_help/main/reference/cgroup/delete.php) пользователей | CAllGroup::Delete | 3.0.10 |
| [OnAfterGroupAdd](/api_help/main/events/onaftergroupadd.php) | после добавления новой группы пользователей | [CAdminTabControl::Begin](/api_help/main/general/admin.section/classes/cadmintabcontrol/begin.php) | 9.5.8 |
| OnAfterGroupUpdate | после изменения группы пользователей | [CGroup::Update](/api_help/main/reference/cgroup/update.php) | 9.5.8 |
| [OnBeforeGroupAdd](/api_help/main/events/onbeforegroupadd.php) | перед добавлением группы пользователей | [CGroup::Add](/api_help/main/reference/cgroup/add.php) | 9.5.8 |
| OnBeforeGroupUpdate | перед изменением группы пользователей | [CGroup::Update](/api_help/main/reference/cgroup/update.php) | 9.5.8 |

### Файлы и права

События при работе с файлами и правами:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnBeforeChangeFile](/api_help/main/events/onbeforechangefile.php) | на изменение файла сразу после его [сохранения](/api_help/main/reference/cmain/savefilecontent.php). | CAllMain::SaveFileContent | 8.5.1 |
| [OnChangePermissions](/api_help/main/events/onchangepermissions.php) | при [изменении прав доступа](/api_help/main/reference/cmain/setfileaccesspermission.php) к файлу или папке. | CAllMain::RemoveFileAccessPermission | 3.0.3 |
| [OnFileDelete](/api_help/main/events/onfiledelete.php) | при удалении файла из таблицы **b\_file**. | [CFile::Delete](/api_help/main/reference/cfile/delete.php) | 10.0.5 |
| OnAfterResizeImage | после изменения размера изображения | [CFile::ResizeImageGet](/api_help/main/reference/cfile/resizeimageget.php) | 10.0.11 |
| OnBeforeChangeFile | перед изменением файла | [CMain::SaveFileContent](/api_help/main/reference/cmain/savefilecontent.php) | 8.5.1 |
| OnBeforeResizeImage | перед изменением размера изображения | [CFile::ResizeImageGet](/api_help/main/reference/cfile/resizeimageget.php) | 10.0.11 |
| OnFileCopy | при копировании файла | [CFile::CopyFile](/api_help/main/reference/cfile/copyfile.php) | 10.0.11 |
| OnFileSave | при сохранении файла Пример использования: при сохранении обрезает оригинал до 1920\*1920   ``` AddEventHandler("main",'OnFileSave','OnFileSave'); function OnFileSave(&$arFile, $fileName, $module) { 	$arNewFile = CIBlock::ResizePicture($arFile, array("WIDTH" => 1920, "HEIGHT" => 1920, "METHOD" => "resample")); 	if(is_array($arNewFile)) 		$arFile = $arNewFile; 	else 		$APPLICATION->throwException("Ошибка масштабирования изображения в свойстве \"Файлы\":".$arNewFile); }Копировать ``` | [CFile::SaveFile](/api_help/main/reference/cfile/savefile.php) | 10.0.11 |
| OnGetFileSRC | при получении адреса изображения | CFile::GetFileSRC | 10.0.11 |
| OnMakeFileArray | при создании массива, описывающего файл | [CFile::MakeFileArray](/api_help/main/reference/cfile/makefilearray.php) | 10.0.11 |
| OnSearchGetFileContent | при индексации модулем поиска | CUserTypeFile::\_\_GetFileContent | 11.0.0 |
| OnTaskOperationsChanged | при изменении уровня доступа | CTask::SetOperations | 11.0.6 |

### Шаблоны почтовых сообщений

События при работе с шаблонами почтовых сообщений:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnBeforeEventMessageDelete](/api_help/main/events/onbeforeeventmessagedelete.php) | перед [удалением почтового шаблона](/api_help/main/reference/ceventmessage/delete.php). | CAllEventMessage::Delete | 3.0.10 |
| [OnEventMessageDelete](/api_help/main/events/oneventmessagedelete.php) | во время [удаления почтового шаблона](/api_help/main/reference/ceventmessage/delete.php) | [CEventMessage::Delete](/api_help/main/reference/ceventmessage/delete.php) | 3.0.10 |
| OnBeforeEventAdd | перед добавлением почтового события | [CEvent::Send](/api_help/main/reference/cevent/send.php) | 6.0.2 |
| [OnBeforeEventSend](/api_help/main/events/onbeforeeventsend.php) | перед отправкой почтового события | CEvent::HandleEvent | 6.0.2 |

### Сайты

События при работе с сайтами:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnBeforeSiteDelete](/api_help/main/events/onbeforesitedelete.php) | перед [удалением сайта](/api_help/main/reference/csite/delete.php). | CAllSite::Delete | 4.0.6 |
| [OnSiteDelete](/api_help/main/events/onsitedelete.php) | в момент [удаления сайта](/api_help/main/reference/csite/delete.php). | CAllSite::Delete | 4.0.6 |
| OnBeforeSiteAdd | перед добавлением сайта в систему | CSite::CheckFields | 9.1.2 |
| OnBeforeSiteUpdate | перед изменением сайта | CSite::CheckFields | 9.1.2 |

### Языки

События при работе с языками:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnAfterLanguageAdd](/api_help/main/events/onafterlanguageadd.php) | после [добавления языка](/api_help/main/reference/clanguage/add.php). | CAllLanguage::Add | 25.0.0 |
| [OnBeforeLanguageDelete](/api_help/main/events/onbeforelanguagedelete.php) | перед [удалением языка](/api_help/main/reference/clanguage/delete.php). | CAllLanguage::Delete | 3.3.21 |
| [OnLanguageDelete](/api_help/main/events/onlanguagedelete.php) | в момент [удаления языка](/api_help/main/reference/clanguage/delete.php) | CAllLanguage::Delete | 3.3.21 |
| OnBeforeLangDelete | перед удалением языка из системы | [CSite::Delete](/api_help/main/reference/csite/delete.php) | 3.0.10 |
| OnLangDelete | при удалении языка из системы | [CSite::Delete](/api_help/main/reference/csite/delete.php) | 3.0.10 |

### Панель управления и админ. часть

События при работе с панелью управления и административной частью:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnPanelCreate](/api_help/main/events/onpanelcreate.php) | в момент сбора данных для построения [панели управления](/api_help/main/reference/cmain/showpanel.php) в публичной части сайта. | CTopPanel::InitPanelIcons | 3.0.14 |
| [OnAdminContextMenuShow](/api_help/main/events/onadmincontextmenushow.php) | при выводе в административном разделе панели кнопок. | [CAdminContextMenu::Show](/api_help/main/general/admin.section/classes/cadmincontextmenu/show.php) | 9.5.10 |
| [OnAdminListDisplay](/api_help/main/events/onadminlistdisplay.php) | при выводе в административном разделе списка элементов. | [CAdminList::Display](/api_help/main/general/admin.section/classes/cadminlist/display.php) | 9.5.10 |
| [OnAdminTabControlBegin](/api_help/main/events/onadmintabcontrolbegin.php) | при выводе в административном интерфейсе формы редактирования. | [CAdminTabControl::Begin](/api_help/main/general/admin.section/classes/cadmintabcontrol/begin.php) | 9.5.10 |
| OnAfterSetOption\_ | после изменения настроек модуля | COption::SetOptionString | 6.5.8 |
| [OnBuildGlobalMenu](/api_help/main/events/onbuildglobalmenu.php) | при построении меню в административной части | CAdminMenu::Init | 6.0.3 |

#### Смотрите также

* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Связи и взаимодействие модулей](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=2825)

### Рейтинги

События при работе с рейтингами:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| OnAddRatingVote | после добавлении голоса за контент. | [CRatings::Add](/api_help/main/reference/cratings/add.php) | 11.0.5 |
| OnAfterCheckAllowVote | после проверки прав на голосование, перед добавление голоса, нужно вернуть массив вида `array('RESULT' => false, 'ERROR_TYPE' => 'тип ошибки', 'ERROR_MSG' => 'текст ошибки')` голос не будет засчитан, если вернуть true голос будет засчитан. | CRatingRule::Add | 11.0.15 |
| OnCancelRatingVote | после отмены ранее отданного голоса за контент. | [CRatings::Update](/api_help/main/reference/cratings/update.php) | 11.0.5 |
| OnAfterUpdateRatingRule | после обновления правила обработки рейтинга | CRatingRule::Update | 9.5.4 |
| OnBeforeDeleteRating | перед удалением рейтинга | [CRatings::Delete](/api_help/main/reference/cratings/Delete.php) | 9.5.0 |
| OnBeforeDeleteRatingRule | перед удалением правила обработки рейтинга | CRatingRule::Delete | 9.5.4 |
| OnGetRatingContentOwner | перед добавлением голоса для определения идентификатора автора контента | [CRatings::AddRatingVote](/api_help/main/reference/cratings/addratingvote.php) | 11.0.0 |
| OnGetRatingRuleConfigs | во время генерации страницы добавления (редактирования) правил обработки для получения настроек правил | CRatingRule::GetRatingRuleConfigs | 9.5.4 |
| OnGetRatingRuleObjects | при вызове правил обработки рейтинга | CRatingRule::GetRatingRuleObjects | 9.5.4 |
| OnGetRatingsConfigs | во время генерации страницы добавления (редактирования) правил обработки для получения объектов голосования к которым могут быть применены правила | [CRatings::GetRatingConfigs](/api_help/main/reference/cratings/getratingconfigs.php) | 9.5.0 |
| OnGetRatingsObjects | во время генерации страницы добавления (редактирования) рейтингов для получения настроек компонентов рейтинга | [CRatings::GetRatingObjects](/api_help/main/reference/cratings/getratingobjects.php) | 9.5.0 |

### Парсинг текста

События при парсинге текста:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| TextParserAfter | после парсинга | CTextParser::convertText | 10.0.2 |
| TextParserAfterTags | после парсинга тегов | CTextParser::convertText | 10.0.2 |
| TextParserBefore | перед парсингом | CTextParser::convertText | 10.0.2 |
| TextParserBeforePattern | перед парсингом | CTextParser::convertText | 10.0.2 |
| TextParserBeforeTags | перед парсингом тегов | CTextParser::convertText | 10.0.2 |
| TextParserVideoConvert | при парсинге тега видео | CTextParser::convert\_video | 10.0.2 |

### Обновление системы

События при обновлении системы:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| OnUpdatesInstalled | после установки обновлений. Имеет единственный параметр: массив вида:  ``` Array ( 	"successModules" => $arSuccessModules, 	"loadModules" => $arLoadModules, 	"errorModules" => $arErrorModules, 	"modulesUpdates" => $arModulesUpdatesКопировать ``` | CUpdateOutput::ShowBlockInfo | 7.0.12 |
| OnModuleUpdate | после обновления модуля | CUpdateClientPartner::UpdateStepModules | 7.1.1 |

### Установка модулей

События при установке модулей:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| OnAfterRegisterModule | после регистрации модуля | [RegisterModule](/api_help/main/functions/module/registermodule.php) | 12.0.8 |
| OnAfterUnRegisterModule | после деинсталляции модуля | [UnRegisterModule](/api_help/main/functions/module/unregistermodule.php) | 12.0.8 |

### Пользовательские поля

События при работе с пользовательскими полями:

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| OnUserTypeBuildList | при построении списка пользовательских полей | CUserTypeManager::GetUserType | 6.0.2 |
| OnUserTypeRightsCheck | при проверке прав доступа на пользовательские поля | GetRights | 6.5.5 |
| OnAfterFetch | после выполнения выборки |  | 12.5.12 |
| onAfterUserTypeUpdate | после обновления пользовательского поля. Аргументы:  * **$arFields** - массив полей после обновления * **$ID** - идентификатор поля. | [CUserTypeEntity](http://dev.1c-bitrix.ru/api_help/main/reference/cusertypeentity/index.php) | 16.5.3 |
| OnAfterUserTypeDelete | после удаления пользовательского поля. Аргументы:  * **$arFields** - массив полей удаленного элемента * **$ID** - идентификатор поля. | [CUserTypeEntity](http://dev.1c-bitrix.ru/api_help/main/reference/cusertypeentity/index.php) | 16.5.3 |

### Прочие события

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| OnAutoSaveRestore | при восстановлении автосохраненных данных | CAutoSave::\_Restore | 11.0.1 |
| OnBeforeLocalRedirect | перед редиректом | [LocalRedirect](/api_help/main/functions/other/localredirect.php) | 6.5.4 |
| OnLocalRedirect | при редиректе | [LocalRedirect](/api_help/main/functions/other/localredirect.php) | 6.5.4 |
| OnCheckListGet | при отправке чеклиста | CCheckList::\_\_construct | 11.0.1 |
| onAfterAjaxResponse | после обработки аяксового запроса к компоненту в аякс-режиме | ExecuteEvents | 7.0.0 |
| OnAfterShortUriAdd | после добавления короткой ссылки | CBXShortUri::Add | 12.5.0 |
| OnBeforeShortUriDelete | перед удалением короткой ссылки | CBXAllShortUri::Delete | 12.5.0 |

Новинки документации в соцсетях:
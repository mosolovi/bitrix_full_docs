[Социальные сервисы](/api_help/socialservices/index.php)

События (доступен с 9.0.0)

События
=======

Модуль Веб-сервисы частично перешел на ядро D7, для основных сервисов можно использовать события таблета `\Bitrix\Socialservices\UserTable`.

| Событие | Вызывается | Метод | C версии |
| --- | --- | --- | --- |
| OnAfterSocServUserAdd | после добавления пользователя через соцсервис | CSocServAuthDB::Add | 12.0.2 |
| OnAfterSocServUserUpdate | после обновления данных пользователя | CSocServAuth::Update | 12.0.2 |
| OnAuthServicesBuildList | при построении списка сервисов авторизации | CSocServAuthManager::\_\_construct | 9.0.0 |
| OnBeforeOpenIDAuthFinalRedirect | перед редиректом на сайт авторизованного через соцсервис пользователя | COpenIDClient::Authorize | 11.0.0 |
| OnBeforeOpenIDUserAdd | перед добавлением пользователя через OpenID авторизацию | COpenIDClient::Authorize | 11.0.0 |
| OnBeforeSocServUserDelete | перед удалением пользователя | CSocServAuth::Delete | 12.0.2 |
| OnPublishSocServMessage | при публикации сообщения соцсервиса | CSocServAuthManager::PostIntoBuzz | 12.0.4 |
| OnFindSocialservicesUser | при поиске пользователя, событие авторизации | CSocServAuthManager::AuthorizeUser | 17.1.0 |

Новинки документации в соцсетях:
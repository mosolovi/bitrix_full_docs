[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnUserLoginExternal (с версии 4.0.6)

OnUserLoginExternal
===================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
mixed
функция-обработчик(
	array &arParams
);Копировать
```

Событие **OnUserLoginExternal** предназначено для возможности проверки имени входа и пароля во внешнем источнике. Обработчики этого события вызываются в методе [CUser::Login](/api_help/main/reference/cuser/login.php), если ни один обработчик события
 **OnBeforeUserLogin** не вернул *false*, перед стандартной проверкой имени входа *arParams**['LOGIN']*, пароля *arParams**['PASSWORD']* и попытки авторизовать пользователя.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | Массив полей для проверки имени входа и пароля:  * **LOGIN** - Логин пользователя * **PASSWORD** - Пароль. Если параметр **PASSWORD\_ORIGINAL** равен"Y", то в данном параметре был передан оригинальный пароль, в противном случае был передан хеш (md5) от оригинального пароля. * **REMEMBER** - Если значение равно "Y", то авторизация пользователя должна быть сохранена в куках. * **PASSWORD\_ORIGINAL** - Если значение равно "Y", то это означает что **PASSWORD** не был сконвертирован в MD5 (т.е. в параметре **PASSWORD** был передан реальный пароль вводимый пользователем с клавиатуры), если значение равно "N", то это означает что **PASSWORD** уже сконвертирован в MD5. |

**Примечание**. Параметр данного обработчика и элементы массива **arParams** являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Если необходимо авторизовать пользователя, то обработчик события должен вернуть идентификатор этого пользователя.

### Смотрите также

* [Событие "OnBeforeUserLogin"](/api_help/main/events/onbeforeuserlogin.php)
* [Событие "OnAfterUserLogin"](/api_help/main/events/onafteruserlogin.php)
* [CUser::Login](/api_help/main/reference/cuser/login.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Внешняя авторизация](http://dev.1c-bitrix.ru/learning/course/index.php?&COURSE_ID=43&LESSON_ID=3574)

### Пример функции-обработчика

```
<?
// пример авторизации пользователя из таблиц форума Innovision Power Board
// файл /bitrix/php_interface/init.php
AddEventHandler("main", "OnUserLoginExternal", Array("__IPBAuth", "OnUserLoginExternal"));
AddEventHandler("main", "OnExternalAuthList", Array("__IPBAuth", "OnExternalAuthList"));
define("IPB_TABLE_PREFIX", "ibf_");
define("IPB_VERSION", "2");
class __IPBAuth
{
	public static function OnUserLoginExternal(&$arArgs)
	{
		$groups_map = Array(
			/*'IPB Group ID' => 'Local Group ID',*/
			'4' => '1'
		);
		$table_user = IPB_TABLE_PREFIX."members";
		$table_converge = IPB_TABLE_PREFIX."members_converge";
		global $DB, $USER, $APPLICATION;
	extract($arArgs);
		if(IPB_VERSION == '1')
		{
			$strSql = "SELECT * FROM ".$table_user." WHERE name='".
				$DB->ForSql($LOGIN)."' AND password='".md5($PASSWORD)."'";
		}
		else
		{
			$strSql =
				"SELECT t1.* ".
				"FROM ".$table_user." t1, ".$table_converge." t2 ".
				"WHERE t1.name='".$DB->ForSql($LOGIN)."' ".
				"    AND t1.email = t2.converge_email ".
				"    AND t2.converge_pass_hash = MD5(CONCAT(MD5(t2.converge_pass_salt), '".md5($PASSWORD)."'))";
		}
		$dbAuthRes = $DB->Query($strSql);
		if($arAuthRes = $dbAuthRes->Fetch())
		{
			$arFields = Array(
				"LOGIN" => $LOGIN,
				"NAME" => $arAuthRes['title'],
				"PASSWORD" => $PASSWORD,
				"EMAIL" => $arAuthRes['email'],
				"ACTIVE" => "Y",
				"EXTERNAL_AUTH_ID"=>"IPB",
				"LID" => SITE_ID
			);
			$oUser = new CUser;
			$res = CUser::GetList($O, $B, Array("LOGIN_EQUAL_EXACT"=>$LOGIN, "EXTERNAL_AUTH_ID"=>"IPB"));
			if(!($ar_res = $res->Fetch()))
				$ID = $oUser->Add($arFields);
			else
			{
				$ID = $ar_res["ID"];
				$oUser->Update($ID, $arFields);
			}
			if($ID>0)
			{
				$USER->SetParam("IPB_USER_ID", $arAuthRes['id']);
				$user_group = $arAuthRes['mgroup'];
				$arUserGroups = CUser::GetUserGroup($ID);
				foreach($groups_map as $ext_group_id => $group_id)
				{
					if($ext_group_id==$user_group)
						$arUserGroups[] = $group_id;
					else
					{
						$arUserGroupsTmp = Array();
						foreach($arUserGroups as $grid)
							if($grid != $group_id)
								$arUserGroupsTmp[] = $grid;
						$arUserGroups = $arUserGroupsTmp;
					}
				}
				CUser::SetUserGroup($ID, $arUserGroups);
				$arParams["STORE_PASSWORD"] = "N";
				return $ID;
			}
		}
	}
	public static function OnExternalAuthList()
	{
		return Array(
			Array("ID"=>"IPB", "NAME"=>"Invision Power Board")
		);
	}
}?>Копировать
```

Новинки документации в соцсетях:
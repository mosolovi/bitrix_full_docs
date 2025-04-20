[Переводы](/api_help/translate/index.php)

CopyMessage (С версии 14.0.0)

CopyMessage
===========

```
CTranslateUtils::CopyMessage(
	$code, 
	$fileFrom, 
	$fileTo, 
	$newCode = ''
);Копировать
```

Метод копирует фразу по четырём языкам: de, en, ru, ua. Метод нестатический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| *code* | Код фразы, которую нужно копировать. |  |
| *fileFrom* | Путь к исходному файлу, где расположена фраза. |  |
| *fileTo* | Путь к файлу куда копируется фраза. |  |
| *newCode* | Новый код фразы. |  |

#### Примеры использования

```
CTranslateUtils::CopyMessage("AD_INSTALL_MODULE_NAME", "C:/Projects/local/bitrix/modules/advertising/install/install.php", "C:/Projects/local/bitrix/modules/advertising/install/index.php");Копировать
```

Новинки документации в соцсетях:
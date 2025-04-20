[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeEventSend (с версии 6.0.2)

OnBeforeEventSend
=================

Вызывается перед отправкой сообщения.

#### Параметры

| Параметр | Описание |
| --- | --- |
| arFields | список переменных |
| arTemplate | массив данных для шаблона |
| context | контекст письма `\Bitrix\Main\Mail\Context`. Параметр используется для разделения потоков писем, путем установки кода категории (потока) писем. |

#### Пример функции-обработчика

```
AddEventHandler('main', 'OnBeforeEventSend', Array("MyForm", "my_OnBeforeEventSend"));
class MyForm
{
	public static function my_OnBeforeEventSend($arFields, $arTemplate)
	{
        
		//получим сообщение
		$mess = $arTemplate["MESSAGE"];
		foreach($arFields as $keyField => $arField)
			$mess = str_replace('#'.$keyField.'#', $arField, $mess); //подставляем значения в шаблон
	}
}Копировать
```

Параметры можно передавать по ссылкам. Вместо:

```
function my_OnBeforeEventSend($arFields, $arTemplate)Копировать
```

Использовать

```
function my_OnBeforeEventSend(&$arFields, &$arTemplate)Копировать
```

Новинки документации в соцсетях:
[Управление структурой](/api_help/fileman/index.php)

[Визуальный редактор](/api_help/fileman/editor/index.php)

[Объект oBXEditorUtils](/api_help/fileman/editor/obxeditorutils/index.php)

BXRemoveAllChild

BXRemoveAllChild
================

Удаляет все дочерние узлы элемента, передаваемого в качестве единственного параметра *pNode*.

```
void
oBXEditorUtils.BXRemoveAllChild(
	object pNode
);Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *pNode* | Узел DOM структуры документа. |

#### Пример использования

```
<script>
var oTable = document.getElementById('tableId');
oBXEditorUtils.BXRemoveAllChild(oTable); //Удаляет дочерние узлы таблицы с id='tableId'
</script>Копировать
```

Новинки документации в соцсетях:
[JS библиотека](/api_help/js_lib/index.php)

[Side Panel](/api_help/js_lib/sidepanel/index.php)

Лоадеры

Лоадеры
=======

Лоадер представляет собой svg-файл, который показывается во время загрузки содержимого слайдера. Для задания лоадера необходимо указать либо полный путь к файлу:

```
BX.SidePanel.Instance.open("/mypage.php", {
	loader: "/images/my-loader.svg"
});Копировать
```

либо идентификатор вида **moduleId:loaderId**

```
BX.SidePanel.Instance.open("/mypage.php", {
	loader: "landing:list" //это превратится в путь /bitrix/images/landing/slider/list.svg
});Копировать
```

Новинки документации в соцсетях:
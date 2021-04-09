# LazyLoading

> Откладывает загрузку изображений на длинных веб-страницах. Изображения за пределами области экрана не будут загружены до того, пока пользователь не доскролит до них.
> Нет никаких зависимостей, только чистый JavaScript.  
> Размер min версии 1кб.   
> Создан на основе [API Intersection Observer](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)

[![License](https://img.shields.io/github/license/bladhard/lazy-loading.svg?style=flat-square)](https://github.com/Bladhard/lazy-loading/blob/main/LICENSE)

## Скачиваем и подключаем
```javascript
// обычную версию
<script src="js/lazyload.js"></script>
// или min версию
<script src="js/lazyload.min.js"></script>

// в основном файле вызываем
LazyLoad()
```

## Как работает

По умолчанию LazyLoading предполагает, что URL-адрес исходного изображения с высоким разрешением можно найти в атрибуте `data-src` или `data-srcset` с классом `lazyload` на изображениии или блоке. Вы также можете включить дополнительный заполнитель с низким разрешением в атрибут `src`.

### img
```html
<!-- img -->
<img class="lazyload" data-src="./img/img-1.jpg" src="data:image/jpeg;base64,UklGRjoAAA">
```

### picture
LazyLoading атоматически определяет поддержку браузером формата `webp` и загрузит `source`, если поддержки нет `img` .
Заполнитель с низким разрешением используем в `img`.

```html
<!-- picture -->
<picture class="lazyload">
    <source data-srcset="./img/img-3.webp" type="image/webp">
    <img data-src="./img/img-3.jpg" src="data:image/jpeg;base64,UklGRjoAAA">
</picture>
```

### div
```html
<div class="lazyload">
    <img data-src="./img/img-2.jpg" src="data:image/jpeg;base64,UklGRjoAAA">
</div>
<div class="lazyload">
    <picture>
        <source data-srcset="./img/img-2.webp" type="image/webp">
        <img data-src="./img/img-2.jpg" src="data:image/jpeg;base64,UklGRjoAAA">
    </picture>
</div>
```

## Настройка
LazyLoading можно настроить, передав дополнительные аргументы.
Подробнее о `root`, `rootMargin`, `threshold` можно почитать на офстранице [API Intersection Observer](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)
### Настройки по умолчанию
```javascript
LazyLoad({
    selector: 'lazyload', // class="lazyload"
    root: null,
    rootMargin: '0px 0px 300px 0px',
    threshold: 0,
})
```

## Donate

<a href="https://www.buymeacoffee.com/bladhard" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" height="38.25px" width="162.75px"></a>

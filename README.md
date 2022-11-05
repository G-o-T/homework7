# homework7

## 1. Как сделать так, чтобы при просмотре на телефоне текст стал читаемым, а картинка - большой? 
    
   Надо позаботиться об адаптивности сайта. Для этого есть ряд способов, один из них - прописать с помощью медиазапросов, каким должен быть текст и размер картинки при заданном размере экрана телефона.
    
## 2. В чём разница между отзывчивым и адаптивным веб-дизайном?
Отзывчивый дизайн (Responsive Design) - дизайн, при котором структура веб-страницы (один макет) автоматически приспосабливается под ширины окон браузереров пользователей, сжимаясь или расширяясь до нужных размеров. А при адаптивном дизайне (Adaptive Design) структура веб-страницы приспосабливается под заданные макеты фиксированной ширины, т.е. приспособление происходит скачкообразно (в брейкпоинтах), поскольку используется несколько макетов для каждого вида устройств.

## 3. Какие величины лучше использовать для шрифтов в гибком дизайне? 
Рекомендуют использовать относительные величины типа rem, em (первое - чаще). Нашла еще такой вариант: для html задается font-size: 10px; а затем используют rem. Например: font-size: 1.6rem. C одной стороны это удобно, т.к. просто высчитать и понять, сколько составляет размер шрифта. С другой - при необходимости сделать шрифт меньше или крупнее можно скорректировать размер font-size для html и пропорционально изменится все.

## 4. Какой вид верстки использован на этой картинке? К какой категории шаблонов он относится? 
Экран слева - верстка не адаптируется под тип устройства, справа - адаптируется. Значит верстка адаптивная, при этом, исходя из постановки вопроса, дизайн отзывчивый, шаблон похож на Column Drop (столбцы отображаются вертикально друг за другом). Но я не понимаю, как по картинке определить это отзывчивый дизайн или адаптивный. Может тут быть прописан отдельный макет для такого размера экрана? Мне кажется, да.
    
## 5. Как задать стили для экранов шириной от 800 до 1200 пикселей? 
Медиазапрос должен содержать логический оператор and. В данном случае так: @media (min-width: 800px) and (max-width: 1200px), если в вопросе имеется в виду до 1200 включительно. Если не включительно - max-width: 1199px.

## 6. Приведите минимум 2 примера как подключать медиазапросы? 
1. через html <link rel="stylesheet" media="screen and (color)" href="test.css">
2. в коде страницы через
<style>
@media (min-width: 800px) and (max-width: 1200px) {
  ... }
</style>
3. внутри таблицы стилей:
@media (min-width: 800px) and (max-width: 1200px) {
  ... }
4. импортировав файл с медиазапросом через @import (как в таблицу стилей, так и в код через тег <style>)

## 7. Как можно задавать гибкие изображения?
1. Использовать для разных разрешений разные размеры картинки (через <img> и <picture>)
2. Использовать max-width в CSS


## 8. Как задать стили только для `landscape` поворота экрана? И что вообще такое `landscape` и чем он отличается от `portrait`?
`landscape` и `portrait` - это ориентации области просмотра (горизонтальная (ширина больше высоты) и вертикальная (высота больше ширины) соответственно). Они используются в функции orientation.
Задать стили только для `landscape` можно с помощью медиа-запроса @media (orientation: landscape).


## 9. Назовите минимум 3 способа как можно тестировать, как выглядит сайт при разных размерах экранов?
- через инструменты разработчика в браузере;
- онлайн сервисы для проверки адаптива (например, http://mattkersley.com/responsive/);
- инструменты от поисковых систем для проверки адаптива (например, Google Mobile Friendly)

## 10. Самостоятельно изучите, как можно подключить несколько картинок разных размеров через один тег `<img>`?
Для этого у тега `<img>` есть атрибуты srcset and sizes, которые позволяют добавить дополнительные изображения с пометками о размерах, чтобы браузер знал, для какого экрана, какое выбрать.

Пример
<img srcset="cat-390w.jpg 390w,
             cat-768w.jpg 768w"
     sizes="(max-width: 390px) 320px,
            (max-width: 768px) 680px,
     src="cat-768w.jpg" alt="Sweet cat">

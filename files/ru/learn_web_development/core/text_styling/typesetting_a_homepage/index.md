---
title: "Задание: Стилизирование школьного сайта"
slug: Learn_web_development/Core/Text_styling/Typesetting_a_homepage
---

{{LearnSidebar}}{{PreviousMenu("Learn/CSS/Styling_text/Web_fonts", "Learn/CSS/Styling_text")}}

В этой оценке мы проверим ваше понимание всех методов стилизации текста, которые мы рассмотрели в этом модуле дав вам задание стилизовать текст домашней страницы общественной школы. Вы можете просто развлечься, выполняя задание.

| Предварительные требования: | Вы должны были изучить все статьи в этом модуле, прежде чем приступать к оценке. |
| --------------------------- | -------------------------------------------------------------------------------- |
| Задача:                     | Проверить понимание методов CSS по стилизации текста.                            |

## Отправная точка

Чтобы начать эту оценку, вам необходимо:

- Перейти и взять файлы [HTML](https://github.com/mdn/learning-area/blob/master/css/styling-text/typesetting-a-homepage-start/index.html) и [CSS](https://github.com/mdn/learning-area/blob/master/css/styling-text/typesetting-a-homepage-start/style.css) для упражнения, а также предоставленную [иконку внешней ссылки](https://github.com/mdn/learning-area/blob/master/css/styling-text/typesetting-a-homepage-start/external-link-52.png).
- Сделайте их копии на вашем компьютере.

В качестве альтернативы, вы можете пользоваться сайтами как [JSBin](https://jsbin.com/) или [Glitch](https://glitch.com/) чтобы выполнить оценку. Вы можете вставить HTML и заполнить CSS в одном из этих онлайн-редакторов и использовать [этот URL](https://mdn.github.io/learning-area/css/styling-text/typesetting-a-homepage-start/external-link-52.png) чтобы указать фоновое изображение. Если же онлайн-редактор, которым вы пользуетесь, не имеет отдельной CSS панели, тогда вводите его в элемент `<style>` в head документа.

> [!NOTE]
> Если вы застрянете, то попросите помощи — см. секцию [Оценка или дальнейшая помощь](#оценка_или_дальнейшая_помощь) в конце этой страницы.

## Краткое описание проекта

Вам предоставлен некоторый "сырой" HTML для домашней страницы воображаемого общественного колледжа, плюс немного CSS который стилизует страницу в макет с тремя колонками и обеспечивает ещё каким-то другим элементарным стилем. Вы должны писать ваш дополнительный CSS после комментария в низу CSS файла, чтобы убедиться, что вы с лёгкостью заметите части проделанные вами. Не переживайте если некоторые селекторы повторяются; мы отпустим вас с этим случаем.

Шрифты:

- Во-первых, загрузите парочку бесплатных для использования шрифтов. Так как это колледж, шрифты должны быть выбраны так чтоб они придавали достаточной серьёзности, формальности и чувства заслуживающего доверия — может подойти шрифт с засечками (serif) для всего основного текста, в сочетании с шрифтами sans-serif или serif для заголовков.
- Используйте подходящий сервис для генерации пуленепробиваемого `@font-face` кода для этих двух шрифтов.
- Примените ваш основной шрифт для всей страницы и шрифт заголовка для заголовков.

Общая стилизация текста:

- Дайте всей странице `font-size` `10px`.
- Дайте вашему заголовку и другим типам элементов подходящие размеры шрифта задаваемые используя соответствующие относительные единицы.
- Дайте основному тексту подходящую `line-height`.
- Отцентрируйте ваш заголовок верхнего уровня на странице.
- Дайте вашим заголовкам немного `letter-spacing` чтобы они не были слишком сжатыми, позвольте буквам немного дышать.
- Дайте основному тексту немного `letter-spacing` и `word-spacing`, при необходимости.
- Дайте первым параграфам после каждого заголовка в `<section>` немного отступа, скажем 20px.

Ссылки:

- Дайте состояниям link, visited, focus, и hover какой-нибудь цвет, который будет сочетается с цветом горизонтальных линий на верху и в низу страницы.
- Сделайте так чтобы ссылки были подчёркнутыми по умолчанию, но, чтобы подчёркивание исчезало, когда вы фокусируетесь или наводите мышь на них.
- Удалите установленный по умолчанию контурный фокус со ВСЕХ ссылок на странице.
- Дайте состоянию active заметно отличимый стиль так чтоб он красиво выделялся, но чтоб он все ещё вписывался в общий дизайн страницы.
- Сделайте так чтоб внешние ссылки имели иконку внешней ссылки, вставленную рядом с ними.

Списки:

- Убедитесь, что интервалы ваших списков и пунктов списка совпадают со стилизацией всей страницы. Все элементы списка должны иметь ту же `line-height` что и строки параграфов, и каждый список должен иметь те же интервалы сверху и снизу которые имеются между параграфами.
- Дайте элементам списка симпатичные маркеры, соответствующие дизайну страницы. Выберете ли вы пользовательские изображения для маркеров или что-то другое — зависит от вас.

Меню навигации:

- Стилизуйте ваше меню навигации так чтоб оно соответствовало внешнему виду страницы.

## Советы и подсказки

- Вам не надо как-либо редактировать HTML в этом упражнении.
- Вам не надо обязательно делать меню навигации в виде кнопок, но надо чтоб они были более-менее высокими, чтобы они не выглядели глупо на краю страницы; также помните, что вам надо сделать его вертикальным меню навигации.

## Пример

Следующий скриншот показывает пример того, как может выглядеть законченный дизайн.

![](example2.png)

## Оценка или дальнейшая помощь

Если вы хотите, чтобы вашу работу оценили, или вы застряли и хотите попросить помощи:

1. Разместите свою работу в онлайн редакторе в которым можно поделиться работами в таком как [CodePen](https://codepen.io/), [jsFiddle](https://jsfiddle.net/), или [Glitch](https://glitch.com/).
2. Напишите пост с просьбой оценки и/или помощи на [MDN Discourse forum Learning category](https://discourse.mozilla.org/c/mdn/learn). Ваш пост должен включать:
   - Описательный заголовок такой как "Требуется оценка вёрстки домашней страницы общественный школы".
   - Детали о том, что вы уже попытались сделать и что бы вы хотели, чтобы мы сделали, например, если вы застряли и вам нужна помощь, либо вы хотите оценку.
   - Ссылку на онлайн редактор (как упомянуто выше в пункте 1) с примером, который нуждается в оценке или с которым нужна помощь. Это хорошая практика чтобы вникнуть — очень сложно помочь кому-либо с проблемным кодом если вы не видите их код.
   - Ссылку на актуальную задачу или страницу оценки, чтобы мы могли найти вопрос, по которому вам нужна помощь.

{{PreviousMenu("Learn/CSS/Styling_text/Web_fonts", "Learn/CSS/Styling_text")}}

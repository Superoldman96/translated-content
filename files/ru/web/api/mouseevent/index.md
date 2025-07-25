---
title: MouseEvent
slug: Web/API/MouseEvent
---

{{APIRef("UI Events")}}

Интерфейс **`MouseEvent`** представляет собой событие, которое происходит в результате взаимодействия пользователя с манипулятором ( например, мышью). Наиболее частые из таких событий: [`click`](/ru/docs/Web/API/Element/click_event), [`dblclick`](/ru/docs/Web/API/Element/dblclick_event), [`mouseup`](/ru/docs/Web/API/Element/mouseup_event), [`mousedown`](/ru/docs/Web/API/Element/mousedown_event).

`MouseEvent` выводится из метода {{domxref("UIEvent")}}, который в свою очередь происходит из метода {{domxref("Event")}}. Метод {{domxref("MouseEvent.initMouseEvent()")}} допустимо использовать для лучшей совместимости с предыдущими версиями, однако, для создания `MouseEvent` рекомендуется использовать конструктор метода {{domxref("MouseEvent.MouseEvent", "MouseEvent()")}}.

Несколько более конкретные события, производные от события mouseevent: {{domxref("WheelEvent")}} and {{domxref("DragEvent")}}.

## Конструктор

- {{domxref("MouseEvent.MouseEvent", "MouseEvent()")}}
  - : Создаёт объект `MouseEvent`.

## Свойства

_Данный интерфейс наследует свойства от родителей {{domxref("UIEvent")}} и {{domxref("Event")}}._

- {{domxref("MouseEvent.altKey")}} {{readonlyinline}}
  - : Возвращает значение `true,` если клавиша&#x20;

    <kbd>alt</kbd>

    &#x20;была нажата во время движения мыши.

- {{domxref("MouseEvent.button")}} {{readonlyinline}}
  - : Представляет код клавиши, нажатой в то время, когда произошло событие мыши.
- {{domxref("MouseEvent.buttons")}} {{readonlyinline}}
  - : Отображает, какие клавиши были нажаты во время движения мыши.
- {{domxref("MouseEvent.clientX")}} {{readonlyinline}}
  - : Отображение X координат курсора мыши в локальной системе координат (DOM контент).
- {{domxref("MouseEvent.clientY")}} {{readonlyinline}}
  - : Отображение Y координат курсора мыши в локальной системе координат (DOM контент).
- {{domxref("MouseEvent.ctrlKey")}} {{readonlyinline}}
  - : Возвращает значение `true,` если клавиша&#x20;

    <kbd>control</kbd>

    &#x20;была нажата во время движения мыши.

- {{domxref("MouseEvent.metaKey")}} {{readonlyinline}}
  - : Возвращает значение `true,` если клавиша&#x20;

    <kbd>meta</kbd>

    &#x20;была нажата во время движения мыши.

- {{domxref("MouseEvent.movementX")}} {{readonlyinline}}
  - : Отображает X координат указателя мыши относительно позиции последнего [`mousemove`](/ru/docs/Web/API/Element/mousemove_event) события.
- {{domxref("MouseEvent.movementY")}} {{readonlyinline}}
  - : Отображает Y координат указателя мыши относительно позиции последнего [`mousemove`](/ru/docs/Web/API/Element/mousemove_event) события.
- {{domxref("MouseEvent.offsetX")}} {{readonlyinline}}{{experimental_inline}}
  - : Отображает X координат указателя мыши относительно позиции границы отступа целевого узла.
- {{domxref("MouseEvent.offsetY")}} {{readonlyinline}}{{experimental_inline}}
  - : Отображает Y координат указателя мыши относительно позиции границы отступа целевого узла.
- {{domxref("MouseEvent.pageX")}} {{readonlyinline}}{{experimental_inline}}
  - : Отображает X координат указателя мыши относительно всего документа.
- {{domxref("MouseEvent.pageY")}} {{readonlyinline}}{{experimental_inline}}
  - : Отображает Y координат указателя мыши относительно всего документа.
- {{domxref("MouseEvent.region")}} {{readonlyinline}}
  - : Возвращает id затронутого событием региона. Если ни какой регион затронут не был, возвращает null.
- {{domxref("MouseEvent.relatedTarget")}} {{readonlyinline}}
  - : Второстепенная цель события, если таковая есть.
- {{domxref("MouseEvent.screenX")}} {{readonlyinline}}
  - : Отображает X координат указателя мыши в пространстве экрана.
- {{domxref("MouseEvent.screenY")}} {{readonlyinline}}
  - : Отображает Y координат указателя мыши в пространстве экрана.
- {{domxref("MouseEvent.shiftKey")}} {{readonlyinline}}
  - : Возвращает true если клавиша&#x20;

    <kbd>shift</kbd>

    &#x20;была нажата, когда произошло событие мыши.

- {{domxref("MouseEvent.which")}} {{non-standard_inline}} {{readonlyinline}}
  - : Возвращает код последней нажатой клавиши, когда произошло событие мыши.
- {{domxref("MouseEvent.mozPressure")}} {{non-standard_inline()}} {{readonlyinline}}
  - : Отображает давление которое было осуществлено при нажатии. Значение будет между `0.0` (минимальное давление) и `1.0` (максимальное давление).
- {{domxref("MouseEvent.mozInputSource")}} {{non-standard_inline()}} {{readonlyinline}}
  - : The type of device that generated the event (one of the `MOZ_SOURCE_*` constants listed below). This lets you, for example, determine whether a mouse event was generated by an actual mouse or by a touch event (which might affect the degree of accuracy with which you interpret the coordinates associated with the event).
- {{domxref("MouseEvent.webkitForce")}} {{non-standard_inline()}} {{readonlyinline}}
  - : Отображает количество приложенного давления при клике.
- {{domxref("MouseEvent.x")}} {{experimental_inline}}{{readonlyinline}}
  - : Alias для {{domxref("MouseEvent.clientX")}}.
- {{domxref("MouseEvent.y")}} {{experimental_inline}}{{readonlyinline}}
  - : Alias для {{domxref("MouseEvent.clientY")}}

## Константы

- {{domxref("MouseEvent.WEBKIT_FORCE_AT_MOUSE_DOWN")}} {{non-standard_inline}}{{readonlyinline}}
  - : Минимальная необходимая сила для обычного клика
- {{domxref("MouseEvent.WEBKIT_FORCE_AT_FORCE_MOUSE_DOWN")}} {{non-standard_inline}}{{readonlyinline}}
  - : Минимальная необходимая сила для усиленного клика

## Методы

_Данный интерфейс наследует свойства от родителей, {{domxref("UIEvent")}} and {{domxref("Event")}}._

- {{domxref("MouseEvent.getModifierState()")}}
  - : Returns the current state of the specified modifier key. See the {{domxref("KeyboardEvent.getModifierState")}}() for details.
- {{domxref("MouseEvent.initMouseEvent()")}} {{deprecated_inline}}
  - : Initializes the value of a `MouseEvent` created. If the event has already being dispatched, this method does nothing.

## Пример

Данный пример демонстрирует симуляцию нажатия левой клавиши мыши (событие мыши генерируется программно) по чекбоксу используя методы DOM.

```js
function simulateClick() {
  var evt = new MouseEvent("click", {
    bubbles: true,
    cancelable: true,
    view: window,
  });
  var cb = document.getElementById("checkbox"); //element to click on
  var canceled = !cb.dispatchEvent(evt);
  if (canceled) {
    // A handler called preventDefault
    alert("canceled");
  } else {
    // None of the handlers called preventDefault
    alert("not canceled");
  }
}
document.getElementById("button").addEventListener("click", simulateClick);
```

```html
<p>
  <label><input type="checkbox" id="checkbox" /> Checked</label>
</p>
<p><button id="button">Click me</button></p>
```

Нажмите на кнопку, чтобы посмотреть, как работает пример.

{{ EmbedLiveSample('Пример', '', '', '') }}

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Посмотрите также

- Its direct parent, {{domxref("UIEvent")}}.

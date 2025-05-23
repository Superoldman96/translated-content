---
title: :default
slug: Web/CSS/:default
---

{{CSSRef}}

**`:default`** は [CSS](/ja/docs/Web/CSS) の[擬似クラス](/ja/docs/Web/CSS/Pseudo-classes)で、関連する要素のグループ内で既定となっているフォーム上の要素を選択します。

{{InteractiveExample("CSS Demo: :default", "tabbed-shorter")}}

```css interactive-example
label,
input[type="submit"] {
  display: block;
  margin-top: 1em;
}

input:default {
  border: none;
  outline: 2px solid deeppink;
}
```

```html interactive-example
<form>
  <p>How did you find out about us?</p>
  <label
    ><input name="origin" type="radio" value="google" checked /> Google</label
  >
  <label><input name="origin" type="radio" value="facebook" /> Facebook</label>
  <p>Please agree to our terms:</p>

  <label
    ><input name="newsletter" type="checkbox" checked /> I want to subscribe to
    a personalized newsletter.</label
  >

  <label
    ><input name="privacy" type="checkbox" /> I have read and I agree to the
    Privacy Policy.</label
  >

  <input type="submit" value="Submit form" />
</form>
```

このセレクターが何に一致するかについては、 [HTML Standard §4.16.3 Pseudo-classes](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-default) で定義されています。 — {{htmlelement("button")}}、[`<input type="checkbox">`](/ja/docs/Web/HTML/Reference/Elements/input/checkbox)、[`<input type="radio">`](/ja/docs/Web/HTML/Reference/Elements/input/radio)、{{htmlelement("option")}} 要素に一致させることができます。

- 既定の option 要素は `selected` 属性が付いた最初のもの、または DOM 順で最初の有効な選択肢です。 `multiple` が付いた {{htmlelement("select")}} は、複数の `selected` がついた選択肢を持つことができますので、すべてが `:default` に一致します。
- `<input type="checkbox">` と `<input type="radio">` は `checked` 属性があるときに一致します。
- {{htmlelement("button")}} は {{htmlelement("form")}} の [既定の送信ボタン](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#implicit-submission)である場合に一致します。フォームに所属する `<button>` のうち、 DOM 順で最初のものです。これはフォームを送信する {{htmlelement("input")}} 型、例えば `image` または `submit` にも適用されます。

## 構文

```
:default
```

## 例

### HTML

```html
<fieldset>
  <legend>Favorite season</legend>

  <input type="radio" name="season" id="spring" />
  <label for="spring">Spring</label>

  <input type="radio" name="season" id="summer" checked />
  <label for="summer">Summer</label>

  <input type="radio" name="season" id="fall" />
  <label for="fall">Fall</label>

  <input type="radio" name="season" id="winter" />
  <label for="winter">Winter</label>
</fieldset>
```

### CSS

```css
input:default {
  box-shadow: 0 0 2px 1px coral;
}

input:default + label {
  color: coral;
}
```

### 結果

{{EmbedLiveSample("Examples")}}

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- [ウェブフォーム — ユーザーデータでの作業](/ja/docs/Learn_web_development/Extensions/Forms)
- [ウェブフォームのスタイル付け](/ja/docs/Learn_web_development/Extensions/Forms/Styling_web_forms)
- 関連する HTML 要素: {{htmlelement("button")}}, [`<input type="checkbox">`](/ja/docs/Web/HTML/Reference/Elements/input/checkbox), [`<input type="radio">`](/ja/docs/Web/HTML/Reference/Elements/input/radio), {{htmlelement("option")}}

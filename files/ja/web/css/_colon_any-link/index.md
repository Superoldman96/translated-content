---
title: :any-link
slug: Web/CSS/:any-link
---

{{CSSRef}}

**`:any-link`** は [CSS](/ja/docs/Web/CSS) の[擬似クラス](/ja/docs/Web/CSS/Pseudo-classes)セレクターで、訪問の有無とは独立したソースアンカーとして振る舞う要素を表します。言い換えれば、 `href` 属性を持つすべての {{HTMLElement("a")}} または {{HTMLElement("area")}} 要素を選択します。つまり、 {{cssxref(":link")}} または {{cssxref(":visited")}} に一致するすべての要素を選択します。

```css
/* :link または :visited に該当するすべての要素を選択 */
:any-link {
  color: green;
}
```

{{InteractiveExample("CSS Demo: :any-link", "tabbed-shorter")}}

```css interactive-example
p {
  font-weight: bold;
}

a:any-link {
  color: forestgreen;
  text-decoration-color: hotpink;
}
```

```html interactive-example
<p>Pages that you might have visited:</p>
<ul>
  <li>
    <a href="https://developer.mozilla.org">MDN Web Docs</a>
  </li>
  <li>
    <a href="https://www.youtube.com/YouTube">Google</a>
  </li>
</ul>
<p>Pages unlikely to be in your history:</p>
<ul>
  <li>
    <a href="https://developer.mozilla.org/missing-3">Random MDN page</a>
  </li>
  <li>
    <a href="https://example.com/missing-3">Random Example page</a>
  </li>
</ul>
```

## 構文

```
:any-link
```

## 例

### HTML

```html
<a href="https://example.com">External link</a><br />
<a href="#">Internal target link</a><br />
<a>Placeholder link (won't get styled)</a>
```

### CSS

```css
a:any-link {
  border: 1px solid blue;
  color: orange;
}

/* WebKit browsers */
a:-webkit-any-link {
  border: 1px solid blue;
  color: orange;
}
```

### 結果

{{EmbedLiveSample('Examples')}}

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- [ハイパーリンクの作成](/ja/docs/Learn_web_development/Core/Structuring_content/Creating_links)
- 一致する HTML 要素: [`<a>`](/ja/docs/Web/HTML/Reference/Elements/a) および [`<area>`](/ja/docs/Web/HTML/Reference/Elements/area) に [`href`](/ja/docs/Web/HTML/Reference/Elements/a#href) 属性が付いたもの
- 関連する CSS セレクター:

  - [`:visited`](/ja/docs/Web/CSS/:visited)
  - [`:link`](/ja/docs/Web/CSS/:link)

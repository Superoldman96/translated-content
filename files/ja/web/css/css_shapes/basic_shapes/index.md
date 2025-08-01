---
title: 基本シェイプ
slug: Web/CSS/CSS_shapes/Basic_shapes
---

CSS のシェイプは {{cssxref("&lt;basic-shape&gt;")}} 型を使用して定義することができ、このガイドでは、この方で受け入れられる様々な値のそれぞれが、どのように動作するかを説明します。単純な円から複雑な多角形までがあります。

シェイプについて見る前に、これらのシェイプを実現するために一緒に使われる二つの情報を理解しておくことに価値があります。

- `<basic-shape>` 型
- 参照ボックス

## \<basic-shape> 型

`<basic-shape>` 型は、すべての基本シェイプを値として使用します。この方は関数表記を使用します。シェイプ型の後に括弧が続き、中にシェイプを説明する追加の値があります。

受け付ける引数は、作成しようとしているシェイプによって様々です。これらは以下の例で説明します。

## 参照ボックス

CSS シェイプで使用される参照ボックスを理解することは、これがそれぞれのシェイプの座標システムを定義するので、基本シェイプを使用するときには重要です。参照ボックスは既に[ボックス値からシェイプを作成するガイド](/ja/docs/Web/CSS/CSS_shapes/From_box_values)で、直接参照ボックスを使用してシェイプを作成するのを見たことがありますね。

Firefox のシェイプインスペクターでは、図形を検査するときに使用中の参照ボックスが表示されるようになっています。下のスクリーンショットでは、 `shape-outside: circle(50%)` を使って円を作りました。浮動要素には 20 ピクセルのパディング、境界、マージンが適用され、シェイプインスペクターはこれらの参照ボックスをハイライト表示します。基本図形を使用する場合、既定で使用される参照ボックスは margin-box です。このスクリーンショットでは、ボックスモデルのその部分を参照して形状が定義されていることがわかります。

![](shapes-reference-box.png)

基本図形を定義した後に、様々なボックス値を追加することができます。したがって、既定の動作は、定義した通りになります。

```css
.shape {
  shape-outside: circle(50%) margin-box;
}
```

したがって、ボックスモデルのさまざまな部分を使用するように、たとえば、境界を使用するように変更することができます。

```css
.shape {
  shape-outside: circle(50%) border-box;
}
```

注目すべきは、 `margin-box` がシェイプを切り取ることです。したがって、マージンボックスからはみ出した他のシェイプを参照して作成されたシェイプは、マージンボックスで切り取られることになります。このことは、以下の基本的な図形の例で見ることができます。

CSS シェイプに適用される参照ボックスの優れた説明については、 [Understanding Reference Boxes for CSS Shapes](http://razvancaliman.com/writing/css-shapes-reference-boxes/) を参照してください。

## inset()

`inset()` 型は矩形を定義します。アイテムを浮動にすると、その周囲に矩形ができるので、あまり有用ではないように見えるかもしれません。しかし、 `inset()` 型はオフセットの定義が可能なので、コンテンツをシェイプの上に引き込むことができます。

したがって、 `inset()` は top, right, bottom, left の 4 つの値に加えて、最後に `border-radius` の値を取ります。以下の CSS は、浮動している要素の参照ボックスから、上下 20 ピクセル、左右 1 0ピクセルの長方形を挿入し、 border-radius の値を 10 ピクセルとします。

```css
.shape {
  float: left;
  shape-outside: inset(20px 10px 20px 10px round 10px);
}
```

マージンの一括指定と同じルールで、一度に複数のオフセットを設定することができます。値が 1 つしかない場合は、すべての辺に適用されます。値が 2 つある場合は、最初の値が上下のオフセットに設定され、 2 番目の値が右と左のオフセットに設定されます。値が 3 つある場合は、 top が 1 番目の値、 left と right が 2 番目の値、 bottom が 3 番目の値に設定されます。値が 4 つある場合は、top、right、bottom、left にそれぞれ適用されます。つまり、上記のルールは次のように表現することもできます。

```css
.shape {
  float: left;
  shape-outside: inset(20px 10px round 10px);
}
```

以下の例では、 `inset()` シェイプを使用して、浮動している要素にコンテンツを引き寄せています。オフセットの値を変更して、シェイプがどのように変化するかを見てみましょう。

{{EmbedGHLiveSample("css-examples/shapes/basic-shape/inset.html", '100%', 800)}}

また、参照ボックスとして使用したいボックス値を追加することもできます。以下の例では、参照ボックスを `margin-box` から `border-box`、`padding-box` または `content-box` に変更すると、オフセットの計算前に開始点として使用する参照ボックスがどのように変化するかを確認することができます。

{{EmbedGHLiveSample("css-examples/shapes/basic-shape/inset-box.html", '100%', 800)}}

## circle()

`shape-outside` の `circle()` 値は 2 つの引数を取ることができます。最初は `shape-radius` です。

`shape-outside` の `circle()` と `ellipse()` の両方の値は、この `<shape-radius>` という引数を受け付けるように指定されています。この引数は長さまたはパーセント値ですが、キーワード `closest-side` や `farthest-side` のいずれかにすることもできます。

**`closest-side`** のキーワードは、シェイプの中心から参照ボックスの最も近い辺までの長さを使用します。円の場合、これは任意の次元で最も近い辺となります。楕円の場合、これはその半径の方向で最も近い辺となります。

**`farthest-side`** のキーワードは、シェイプの中心から参照ボックスの最も遠い辺までの長さを使用します。円の場合、これは任意の次元で最も遠い辺となります。楕円の場合、これはその半径の方向で最も遠い辺となります。

第 2 引数には `position` を指定します。省略した場合は `center` に設定されます。しかし、ここでは、円の中心の位置を示すために、任意の有効な位置を使用することができます。

この円は半径の値を 1 つ受け取ります。半径は長さ、パーセント値、または closest-side、farthest-side のキーワードで、オプションでキーワード **at** とその後に位置の値を指定することができます。

以下の例では、幅 100 ピクセル、余白20ピクセルのアイテムに円を作成しました。これにより、参照ボックスの幅は合計で 140 ピクセルになります。シェイプの半径の値を 50% に設定し、半径を 70 ピクセルに設定しました。そして、位置の値を 30% に設定した。

{{EmbedGHLiveSample("css-examples/shapes/basic-shape/circle.html", '100%', 800)}}

ライブサンプルでは、半径の大きさを変えたり、ポジションの値で円を動かしたり、 `inset()` で行ったように参照ボックスを設定することで、円の大きさを拡大縮小して遊ぶことができます。

追加の例として、 position に `top left` というキーワードを使用すると、ページの左上隅に 1/4 の扇形を作ることができます。以下の例では、生成コンテンツを使って、テキストが流れるような 1/4 の扇形を作成しています。

{{EmbedGHLiveSample("css-examples/shapes/basic-shape/circle-generated.html", '100%', 700)}}

### 図形はマージンボックスで切り取られる

参照ボックスの説明の際に、 margin-box ではシェイプが切り取られることを説明しました。これは、位置を 60% に設定して、円の中心をコンテンツの方に移動させることで確認できます。円の中心はコンテンツに近くなり、円は margin-box を越えて広がっています。これは、広がった部分が切り取られ、四角くなることを意味します。

```css
img {
  float: left;
  shape-outside: circle(50% at 60%);
}
```

![円形はマージンボックスで切り取られる](shapes-circle-clipped.png)

## ellipse()

楕円は基本的に円をつぶしたものなので、 `ellipse()` は `circle()` ととてもよく似た動作をしますが、 x と y の 2 つの半径をこの順番で指定しなければならない点が異なります。

そして、これらの半径の後に `circle()` と同様に位置を指定して、楕円の中心を移動させることができます。以下の例では、 x の半径が 40%、 y の半径が 50%、位置が left の楕円を作成しています。これは、楕円の中心がボックスの左端にあることを意味し、テキストを囲むための半分の楕円の形が得られます。これらの値を変更することで、楕円の形がどのように変化するかを確認できます。

{{EmbedGHLiveSample("css-examples/shapes/basic-shape/ellipse.html", '100%', 800)}}

キーワード値である `closest-side` と `farthest-side` は、浮動要素の参照ボックスの大きさに基づいて、素早く楕円を作成するのに便利です。

{{EmbedGHLiveSample("css-examples/shapes/basic-shape/ellipse-keywords.html", '100%', 800)}}

## polygon()

最後の基本図形は最も複雑なもので、 `polygon()` を作成することによって多くの辺を持ったシェイプを作成することができます。この図形は、 3 つ以上の値の組を受け付けます（多角形は少なくとも三角形を描かなければなりません）。これらの値は、参照ボックスを基準にして描かれた座標です。

下の例では、`polygon()` を使って、テキストを追うための形状を作成しました。どの値を変更しても、形状がどのように変化するかを見ることができます。

{{EmbedGHLiveSample("css-examples/shapes/basic-shape/polygon.html", '100%', 800)}}

ここで、多角形の形状を作成するのに、 Firefox のシェイプインスペクターがとても便利であることが分かるかもしれません。下のスクリーンショットは、このツールで強調された形状を示しています。

![シェイプインスペクターで強調表示されたポリゴンの基本シェイプ](shapes-polygon.png)

もう一つの有用なリソースは [Clippy](https://bennettfeely.com/clippy/) です。これは `clip-path` 用のシェイプを作成するツールですが、基本シェイプの値は `clip-path` で使われるものと同じだからです。

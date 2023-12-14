---
title: 'JestのtoBe()を知る - To be, or not to be, that is the question.'
emoji: "🎭"
type: "tech"
topics: ["jest", "javascript", "test"]
published: false
publication_name: "cybozu_frontend"
---

:::message
この記事は[Cybozu Frontend Advent Calendar 2023](https://adventar.org/calendars/9255)の20日目です。
:::

こんにちは！サイボウズ株式会社フロントエンドエンジニアの [おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com) です。

JavaScriptのテスティングフレームワークの定番である[Jest](https://jestjs.io/ja/)には、`toBe()`という便利なMatcher（評価用関数）が用意されています。

`toBe()`は`expect(A).toBe(B)`の形式で記すことで`A`と`B`が等しいかどうかを評価してくれるのが特徴で、最も基本的な存在なのでテストコード初心者の方も多用されていることと思います。しかし、`toBe()`の挙動を正しく認識しておかないと、思わぬミスを招きかねません。そこで、この記事では、ある2つの値が`toBe()`で等価判定されるのか、はたまた等価判定されない`not.toBe()`なものなのかを見ながら、その挙動に迫ります。

この記事は執筆時点の最新版である[jest@29.7.0](https://github.com/jestjs/jest/releases/tag/v29.7.0)の挙動に基づいています。

# `toBe()`, or `not.toBe()`?

> To be, or not to be, that is the question.
> 『ハムレット』第3幕第1場より

上に示したハムレットの有名な独白には様々な解釈と日本語訳が存在することが知られていますが、この章ではシンプルに各ケースで`expect(A).toBe(B)`と`expect(A).not.toBe(B)`のどちらでテストがパスするのか（＝前者でパスするか否か）を見ていきます。

## 基本編

### Q1

まずはこちらから。

```js
expect(1 + 2).toBe(3);
```

ごく基本的な`number`型の整数同士です。これはみなさんの想像通り、`toBe()`が正解です！つまり、上のコードはパスします。

これに限らず、`string`型や`boolean`型をはじめとするプリミティブデータ型同士の比較は、原則として`toBe()`で等価を確認できます。

```js
// これらは全てパスします
expect(null).toBe(null);           // null
expect(undefined).toBe(undefined); // undefined
expect(true).toBe(true);           // boolean
expect(0.1).toBe(0.1);             // number
expect(10n).toBe(10n);             // bigint
expect("Hello!").toBe("Hello!");   // string
```

ちなみに、`null`と`undefined`はそれぞれ`.toBeNull()`と`.toBeUndefined()`で比較することもできます。これらは`toBe()`よりも失敗時の出力が簡潔になっています。

![](/images/tobe_or_not_tobe/tobenull_tobeundefined.png)
_`toBeNull()`と`toBeUndefined()`は`toBe()`よりも出力がスッキリしている_

## 数値編

プリミティブデータ型の中でも数値周りには取り扱いに注意が必要なケースがいくつかあります。

### Q2

こちらはどうでしょうか？

```js
expect(0.1 + 0.2).toBe(0.3);
```

手計算すると`0.1 + 0.2 = 0.3`なので`toBe()`で正しそうですが、実は`not.toBe()`です。つまり、上のコードはパスしません。

なぜならば、`0.1`や`0.2`のような小数（浮動小数点数）やその計算結果には、内部値にごく小さな誤差が生じることがあり、その場合に正確な計算結果と完全には一致しないからです。

```js
expect(received).toBe(expected) // Object.is equality

Expected: 0.3
Received: 0.30000000000000004 // <-- 0.1 + 0.2の計算結果は0.3ピッタリでない

   5 |
   6 |   test("0.1 + 0.2 = 0.3", () => {
>  7 |     expect(0.1 + 0.2).toBe(0.3);
     |                       ^
   8 |   });
```

こういうときは、両者の近似的な比較をしてくれる`toBeCloseTo()`を使いましょう。`toBeCloseTo()`を使うとデフォルトでは両者の差が`±0.005`未満ならばパスします。

```js
// これはパスします
expect(0.1 + 0.2).toBeCloseTo(0.3);
```

**浮動小数点数に潜むごく小さな誤差は、Jestに限らずJavaScript（ひいてはプログラミング言語全般）を扱う上での基本的な注意点です！**

### Q3

ものすごく大きい数値を使ったこちらはどうでしょうか？

```js
// 1京 vs 1京1
// JavaScriptでは数字をアンダースコアで区切ることができる
expect(1_0000_0000_0000_0000).toBe(1_0000_0000_0000_0001);
```

1京と1京1は明らかに異なる数値なので`not.toBe()`になりそうなものですが、実際は`toBe()`です。上のコードはパスしてしまいます。

なぜならば`number`型では絶対値が$2^{53}$（およそ9007兆）以上の整数を正確に表現できず、指定した通りの値が内部で扱われるとは限らないからです。

![](/images/tobe_or_not_tobe/too_large_number.png)
_大きすぎる数値リテラルに対する警告_

ちなみに、このような下限／上限値は`Number.MIN_SAFE_INTEGER`と`Number.MAX_SAFE_INTEGER`でそれぞれ取得することができます。

https://developer.mozilla.org/ja/docs/Web/JavaScript/Data_structures#%E6%95%B0%E5%80%A4%E5%9E%8B

限度を上回る整数値を扱う場合は、`bigint`型を使いましょう。整数値の末尾に`n`と付けるだけでOKです。

```js
// bigint型同士の比較ならば、not.toBe()でちゃんとパスする
expect(1_0000_0000_0000_0000n).not.toBe(1_0000_0000_0000_0001n);
```

## Truthy / Falsy編

JavaScriptでは、`if`文や`for`文の条件式に`boolean`型以外の値を指定した場合でも、型変換を通じてその値が`true`か`false`かを判定してくれます。このとき、`true`と判定される値を**truthy**、`false`と判定される値を**falsy**と呼びます。

例えば`null`, `undefined`, `0`, `""`（空文字）などの値がfalsyで、それ以外の値はtruthyです。

```js
if (null) {
  // nullはfalsyなので、ここは実行されない
}
```

### Q4

ではこちらはどうでしょうか？

```js
expect(null).toBe(false);
```

`null`はfalsyですが、`not.toBe()`です。上のコードはパスしません。

これは、`toBe()`は両者の比較にあたって`==`演算子で比較するときような**型変換を行わない**からです。`boolean`型の値においては`true`同士 / `false`同士で一致しなければパスしません。

Jestでは、truthy / falsyの判定を行うための`toBeTruthy()`と`toBeFalsy()`が用意されています。truthy / falsyを判定するにはこちらを使用しましょう。

```js
// これはパスします
expect(null).toBeFalsy();
```

ただし、これでは`true` / `false`以外の値もパスしうるので、`boolean`型の値を厳密に評価したいときは引き続き`toBe()`を使うのが吉です。

## 配列 / オブジェクト編

今まではプリミティブデータ型を扱ってきました。ここでは配列やオブジェクトなどのプリミティブデータ型でない値の場合を見ていきましょう。

### Q5

同じ中身で構成された簡単な配列・オブジェクト同士の比較です。

```js
// 配列
expect([1]).toBe([1]);
// オブジェクト
expect({ a: 10 }).toBe({ a: 10 });
```

こちら、両方とも`not.toBe()`です。上のコードはパスしません。

JavaScriptにおけるオブジェクトは**参照型**と呼ばれるものであり、プリミティブデータ型と違って変数には値そのものではなく、その値が格納されているメモリ領域を指す**参照**が格納されます。

上の例の`expect({ a: 10 })`と`.toBe({ a: 10 })`にある`{ a: 10 }`は同じプロパティを持っていますが、それぞれ別に宣言されたものであり、別のメモリ領域を指す別物のオブジェクトなので、`toBe()`で比較すると異なるものとして判定されてしまいます。これは、**オブジェクトの一種である配列についても同様です**。

逆に言うと、比較対象の参照が共に同じならば良いので、次の例はパスします。

```js
// これはパスします
const obj1 = { a: 10 };
const obj2 = obj1;
expect(obj1).toBe(obj2);
```

異なる配列やオブジェクトの中身の一致をテストしたいことは多いと思います。そんなときは、`toEqual()`を使いましょう。`toEqual()`はオブジェクトの中身（各プロパティ）を比較してくれます。

```js
// これはパスします
expect([1]).toEqual([1]);
expect({ a: 10 }).toEqual({ a: 10 });
// 日付も比較できる！
expect(new Date("2023-12-20")).toEqual(new Date("2023-12-20"));
```

ただし、`toEqual()`では`undefined`なキーを無視することがあるなど、やや厳密性に欠ける部分があるので、より厳密な比較をしたいときは、`toStrictEqual()`がオススメです。

```js
// これはパスします
expect([1, 2, undefined]).toEqual([1, 2]);
expect({ a: undefined }).toEqual({});
// これはパスしない
expect([1, 2, undefined]).not.toStrictEqual([1, 2]);
expect({ a: undefined }).not.toStrictEqual({});
```

以上、クイズでした！何問正解できましたか？

# `toBe()`がやってくれること

ここまで具体例とともに`toBe()`の挙動を見てきましたが、`toBe()`の比較の挙動は実はシンプルで、**`Object.is(A, B)`を実行しているだけです**。このことは[Jestのドキュメント](https://jestjs.io/ja/docs/expect#tobevalue)に明記されている他、ソースコードを見ても分かります。

https://github.com/jestjs/jest/blob/v29.7.0/packages/expect/src/matchers.ts#L77-L85

`Object.is()`は、2つの値が機能的に同一かを評価します。プリミティブデータ型の値が等しいかどうか、参照型の値が同じ参照を持つかどうかを**型変換を行わずに**判定する点は、厳密等価の演算子`===`と同じです。しかし、`===`とは微妙に異なる点が2つあります。

1. 3つのゼロ値`+0`と`0`と`-0`について、`+0 vs -0`、`0 vs -0`を`===`は等価であると判定しますが、`Object.is()`は**等価でない**と判定します。
   - ちなみに`+0 vs 0`は`===`も`Object.is()`も等価であると判定します。
1. `NaN vs NaN`を`===`は等価でないと判定しますが、`Object.is()`は**等価である**と判定します。

```js
// これらは全てパスする
// 1. +0, 0, -0の比較
expect(+0).not.toBe(-0);
expect(0).not.toBe(-0);
expect(+0 === -0).toBe(true);
expect(0 === -0).toBe(true);
// 2. NaNの比較
expect(NaN).toBe(NaN);
expect(NaN === NaN).toBe(false);
```

https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Object/is

ただし、こうした例外はテストを実装していてそう頻繁に出てくるわけではないので、「`toBe()`は`===`とほぼ同じだけど、ゼロとNaN周りは注意しないと」くらいの認識で特段問題ないかなと思います。

# まとめ

JavaScriptのテスティングフレームワーク・[Jest](https://jestjs.io/ja/)のMatherの中で最も基本的なものである`toBe()`の挙動を、キワドイ例とともに確認してきました。

`toBe()`はJestの最も基本的なMatcherで、等価判定条件は`Object.is()`と全く同じ（`===`と**ほとんど**同じ）という点で非常にシンプルですが、いざ活用するとなると、数値やオブジェクトの扱いなど、JavaScriptの仕様が絡む注意点がいくつか潜んでいることが分かりました。

テスティングフレームワークのことだけでなく、その根底にあるプログラミング言語の動きについても理解を深めて、より間違いの少ないテストコードを書くことができるよう努めていきたいですね。

また、Jestには今回紹介したもの以外にも痒い所に手が届くMatcherがたくさん用意されているので、ぜひ公式ドキュメントを読んでみてください！

https://jestjs.io/ja/docs/expect
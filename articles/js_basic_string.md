---
title: 'この夏押さえておきたいJavaScriptの文字列操作コレクション'
emoji: "🏄"
type: "tech"
topics: ["javascript"]
published: false
publication_name: "cybozu_frontend"
---

:::message
この記事は、[CYBOZU SUMMER BLOG FES '25](https://cybozu.github.io/summer-blog-fes-2025/)の記事です。
:::

こんにちは！サイボウズ株式会社フロントエンドエンジニアの [おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com) です。

サイボウズの技術ブログの夏フェス・[CYBOZU SUMMER BLOG FES '25](https://cybozu.github.io/summer-blog-fes-2025/)が7月14日(月)から始まってます！企画の一環として、フロントエンドの記事が9月いっぱいまで**毎週木曜日**に投稿されますので、みなさんお楽しみに！

今回は、コーディングに手放せない存在の1つ「**文字列**」をテーマに、JavaScriptの文字列操作の中でも普段使いしやすいものをピックアップして、細かいテクニックを交えながらお届けします。

身近ながらも今まで見落としていたポイントを拾ってもらえたらと思います！

以前は「配列」をテーマに同じような記事を書きました。こちらも合わせてご覧ください。

https://zenn.dev/cybozu_frontend/articles/js_basic_array

:::message

以降のコードブロックの凡例です。
```js
const str = 'hello,' + 'world!'
str // console.logした出力結果 ← 出力結果に対するコメント
```

:::

# 文字列を作る

文字列は、その名の通り文字の羅列を扱えるものです。JavaScriptにおける文字列はプリミティブのものとオブジェクトのものがありますが、プリミティブを扱うことが多いです。

文字列を1から作成する方法はたくさんあります。

```js
// 文字列のプリミティブ
'Alice and Bob'
"Alice and Bob"
`Alice and Bob`
String('Alice and Bob')
// 文字列のオブジェクト
new String("Alice and Bob")
```

`'`または`"`で囲んだものは文字列リテラルと呼ばれます。どちらで囲んでも効果は変わりません。`` ` ``で囲んだものはテンプレートリテラルと呼ばれ、他と異なる機能を有します（後述）。

`String()`と`new String()`は引数に文字列以外を入れると文字列に変換します。

```js
String(731)  // '731' ← 文字列のプリミティブ
new String(731) // String {'731'} ← 文字列のオブジェクト
```

他にも文字列を作る方法はたくさんありますが、後で主なものをユースケース別に紹介します。

:::details 文字列のプリミティブとオブジェクトの違い

文字列にはプリミティブのものとオブジェクトのものがあります。

前者は、Javascriptに存在する7種類のプリミティブの1つで、`typeof`を使うことで確かめられます。さまざまな特徴がありますが、例えば同じ文字列ならば等価判定されます。

```js
const a = 'hello'
const b = 'hello'
typeof a // 'string'
a === b // true
```

一方で、文字列のオブジェクトは`String`オブジェクトというもので、その名の通りオブジェクトです。`typeof`を使うと`'object'`と返ります。また、例え文字列が同じでも参照が異なるなら比較しても等価になりません。

```js
const a = new String('hello')
const b = new String('hello')
typeof a // 'object'
a === b // false
```

`String`オブジェクトには組み込みで数多くのメソッドが用意されています。例えば、`.toString()`メソッドを使うと文字列のプリミティブを得られます。

```js
const a = new String('hello')
a // String { 'hello' } ← 文字列のオブジェクト
a.toString() // 'hello' ← 文字列のプリミティブ
typeof a            // 'object'
typeof a.toString() // 'string'
```

ちなみに、**文字列のプリミティブに対して`String`オブジェクトのメソッドを使用することもできます**。文字列のプリミティブは`String`オブジェクトではないものの、内部処理で必要に応じて一時的に`String`オブジェクトに変換されます。このようなオブジェクトをラッパーオブジェクトと呼びます。ラッパーオブジェクトは、他にも論理型のプリミティブ（`true`/`false`）に対する`Boolean`オブジェクトなどがあります。

```js
// 文字列のオブジェクト
const a = new String('hello')
a.toUpperCase() // 'HELLO'
// 文字列のプリミティブ
'hello'.toUpperCase() // 'HELLO' ←いける！
```

宣言や比較の容易さなどから、文字列のオブジェクトよりも文字列のプリミティブの方が実用的なので、特段の意図がない限り文字列のプリミティブを利用するのが基本的だと思います。

:::

# 文字列の長さを得る

```js
'hello'.length // 5
''.length  // 0
```

文字列の長さは`str.length`で取得できます。配列と同様です。

```js
'吉野家'.length // 3
'𠮷野家'.length // 4 ← ?
```

多くの文字列の長さは文字の個数と等しくなりますが、文字によっては1文字が複数カウントされます。これは`str.length`ではUTF-16のコード単位（2バイト値）の個数を数えており、UTF-16ではUnicode文字の種類によっては2つのコード単位で表現されるからです。例えば「吉」は`\u5409`なので1カウントですが、「𠮷」は`\uD842\uDFB7`なので2カウントされます。

文字の個数（書記素クラスターと呼ばれます）を数えたいときは`Intl.Segmenter`を利用することができます。

```js
const s = new Intl.Segmenter();
[...s.segment('吉')].length // 1
[...s.segment('𠮷')].length // 1
```

# 文字列を操作する

JavaScriptには文字列をいじるための方法がたくさん用意されています。知っていると便利なものをいくつか紹介します。

## 文字をくっつける

```js
'Hello' + ', ' + 'World!' // 'Hello, World!'
'Score: ' + 100           // 'Score: 100'

let str = 'Hello, '
str += 'World!'
str // 'Hello, World!'
```

文字列は`+`演算子を用いて連結できます。とてもシンプルですね。`文字列 + 数値`のように一方が文字列でなければ、文字列に変換されて連結されます。加算代入演算子`+=`も使えます。

```js
'Hello'.concat(', ', 'World', '!') // 'Hello, World!'
'Score: '.concat(100)              // 'Score: 100'

const ymca = ['Y.', 'M.', 'C.', 'A.']
''.concat(...ymca) // 'Y.M.C.A.'
```

`str.concat()`を用いて複数の文字列を結合することもできます。スプレッド構文`[...arr]`を用いると配列の全要素を丸ごと連結できます。

```js
['Hello', 'World!'].join(', ')  // 'Hello, World!'
['2025', '07', '31'].join('-') // '2025-07-31'
['A', 'B', 'C'].join('')       // 'ABC'
```

配列にある文字列の連結には`str.join()`が便利です。引数に与えた文字列が間に挟まります。

```js
const name = 'Alice'
const age = 20
`Hello, ${name}!` // 'Hello, Alice!'
`${name} is ${age} years old` // 'Alice is 20 years old'

`2 + 3 = ${2 + 3}` // '2 + 3 = 5' ← 計算もできる

`Line 1
Line 2` // 'Line 1\nLine 2' ← 改行が反映される
```

文字列の連結とは少しニュアンスが異なりますが、ある文字列に別の文字列を埋め込むことができます。

`` ` ``で囲んだ文字列（テンプレートリテラル）では、その内部で`${}`を使うことで別の文字列を埋め込めます。`${}`の中には数値や計算式などを入れることもでき、その時は計算結果を文字列に変換したものが埋め込まれます。

文字列リテラルと異なり、テンプレートリテラルでは内部の改行が改行コードとして扱われます。

## 文字を分割する

```js
'2025-07-31'.split('-')   // ['2025', '07', '31']
'Hi!'.split('')           // ['H', 'i', '!'] ←空文字列だと文字ごとに分割
'A1B2C3'.split(/\d/)      // ['A', 'B', 'C', ''] ←正規表現も使える
'A,B,C,D,E'.split(',', 3) // ['A', 'B', 'C'] ←配列の最大長を制限
```

文字列を指定した区切り文字で分割し、配列にまとめることができます。区切り文字には正規表現も使えます。

## 文字を取ってくる

```js
const str = 'Hello'

// 実は添え字番号で指定できる
str[0]  // 'H'
str[-1] // undefined ← 負の値
str[10] // undefined ← 範囲外

// charAtメソッドを使う方法
str.charAt(0)  // 'H'
str.charAt(-1) // '' ← 負の値
str.charAt(10) // '' ← 範囲外

// atメソッドを使う方法
str.at(0)  // 'H'
str.at(-1) // 'o' ← 末尾の文字
str.at(10) // undefined ← 範囲外
```

`str.at()`は、他と異なり**引数が負の値の時に末尾から前に数えた文字を手に入れることができる**ので便利です。末尾の文字を得るために`str.charAt()`では`str.charAt(str.length - 1)`とすべきところ、`str.at()`では`str.at(-1)`で済みます。

## 文字列の一部を取ってくる

```js
const str = 'Hello, World!'

// substringメソッドを使う方法
str.substring(0, 5) // 'Hello'
str.substring(7)    // 'World!'' ← 終了位置を省略すると末尾まで
str.substring(-6)   // 'Hello, World!' ← 負の値は0として扱われる
str.substring(5, 0) // 'Hello' ← 開始位置の方が大きいなら引数を交換して扱う

// sliceメソッドを使う方法
str.slice(0, 5)   // 'Hello'
str.slice(7)      // 'World!' ← 終了位置を省略すると末尾まで
str.slice(-6)     // 'World!' ← 負の値で末尾から数える
str.slice(5, 0)   // '' ← 開始位置の方が大きいなら空文字列
```

どちらも指定した開始位置から終了位置までの部分文字列を返します。いずれも**終了位置の文字は含まれません**。

`str.substring()`は負の値が`0`として扱われる一方、`str.slice()`は末尾から数えた位置になります。また、開始位置が終了位置より大きいときの挙動も異なります。

## 文字列を検索する

### 単にあるか知りたい

```js
const str = 'Hello, World!'

// startsWithメソッドを使う方法
str.startsWith('Hello')    // true
str.startsWith('World')    // false
str.startsWith('World', 7) // true ← 7番目から'World'で始まるか

// endsWithメソッドを使う方法
str.endsWith('!')         // true
str.endsWith('World')     // false
str.endsWith('World', 12) // true ← 12番目までが'World'で終わるか
```

これらは、ある文字列が第1引数に入れた文字列で始まるか・終わるかを確かめられます。意外にも第2引数が存在していて、どの位置から始まるか・どの位置で終わるかを指定できる柔軟さがあります。

```js
const str = 'Hello, World!'
str.includes('Wo') // true
str.includes('Wo', 10)  // false ← 10番目以降に'Wo'があるか
```

文字列の中に指定した文字列が含まれているかを確かめるには`str.includes()`が使えます。こちらも第2引数で検索開始位置を指定できます。

```js
const reg = /^Hello/
const str = 'Hello, World!'
reg.test(str) // true
```

正規表現を用いて検索する方法もあります。正規表現に関する組み込みオブジェクトである`RegExp`オブジェクトが提供する`reg.test()`は、引数に与えた文字列がその正規表現に当てはまるならば`true`を返します。

### どこにあるか知りたい

```js
const str = 'Hello, World! Hello!'

// indexOfメソッドを使う方法
str.indexOf('Hello')    // 0
str.indexOf('World')    // 7
str.indexOf('hello')    // -1 ← 見つからない（大文字小文字を区別）
str.indexOf('Hello', 1) // 14 ← 1番目以降で検索

// lastIndexOfメソッドを使う方法
str.lastIndexOf('Hello') // 14 ← 最後に現れる位置

// searchメソッドを使う方法
str.search(/,/)     // 5 ← カンマが最初に現れる位置
str.search(/[A-Z]/) // 0 ← 大文字が最初に現れる位置
str.search(/Good/)  // -1 ← 見つからない
```

引数に入れた文字列のヒット位置を返すメソッドがいくつかあります。`str.indexOf()`と`str.lastIndexOf()`は文字列を与えますが、`str.search()`は正規表現を与えます。

### 合致したものを得たい

```js
const str = 'id-1234,id-5678'

// matchメソッドを使う方法
str.match(/id-(\d+)/g) // ['id-1234', 'id-5678']
str.match(/id-(\d+)/)  // ['id-1234', '1234']
str.match(/id-1111/g)  // null ← 見つからない

// matchAllメソッドを使う方法
const matches = str.matchAll(/id-(\d+)/g)
for (const match of matches) {
  match // 1回目: ['id-1234', '1234']
        // 2回目: ['id-5678', '5678']
}
[...matches] // [
             //   ['id-1234', '1234'],
             //   ['id-5678', '5678']
             // ] ←スプレッド構文で配列化できる！
str.matchAll(/id-(\d+)/) // エラー
```

ある正規表現のパターンに合致する箇所を取得できます。

`str.match()`では、`g`フラグがあればパターンに合致する文字列を**全て**返し、`g`フラグがなければ`()`で囲んだ中のパターン（キャプチャグループ）に一致する文字列も一緒に得られます。キャプチャグループは文字列の一部に含まれるIDなどを取得するのに便利です。

`str.matchAll()`は合致するパターンを全て返す上、キャプチャグループに一致する文字列も返してくれます。ただし、返り値は配列でなくイテレータである点に注意が必要です。イテレータは`for...of`文でループを回せますし、スプレッド構文`[...matches]`で配列化できます。また与える正規表現に`g`フラグがなければ例外が投げられます。

| メソッド | 複数検索 | キャプチャグループ |
| :--- | :--- | :--- |
| `str.match()`（`g`あり） |◯|×|
| `str.match()`（`g`なし） |×（最初に一致したものだけ）|◯|
| `str.matchAll()` |◯|◯|

## 文字列を置換する

```js
const str = 'Hello, World! Hello!'

// replaceメソッドを使う方法
str.replace('Hello', 'Hi')  // 'Hi, World! Hello!'
str.replace(/Hello/g, 'Hi') // 'Hi, World! Hi!' ← 全て置換
str.replace(/Hello/g, (m) => m.toUpperCase())
// 'HELLO, World! HELLO!' ← 関数を使った置換もできる！

// replaceAllメソッドを使う方法
str.replaceAll('Hello', 'Hi')  // 'Hi, World! Hi!' ← 全て置換
str.replaceAll(/Hello/g, 'Hi') // 'Hi, World! Hi!' ← 全て置換
str.replaceAll(/Hello/, 'Hi')  // エラー
```

これらは、第1引数に合致する部分を第2引数に置き換えます。いずれも第1引数には正規表現を与えることができ、第2引数にはどう置換するかを示す関数を入れることもできます。検索パターンも置換パターンも柔軟に設定できる便利なメソッドです。

`str.replace()`は最初に合致した1つだけを置換する（`g`フラグがある正規表現を指定したときは例外）のに対して、`str.replaceAll()`は全ての合致箇所を置き換えます。`str.replaceAll()`は、与える正規表現に`g`フラグがなければ例外が投げられます。

## 文字を埋め尽くす

```js
const str = '5'

// padStartメソッドを使う方法
'Hi'.padStart(10)        // '        Hi'
'Hi'.padStart(10, '.,*') // '.,*.,*.,Hi'
'Hello'.padStart(3, '*') // 'Hello' ←元の文字列より数字が小さいとき

// padEndメソッドを使う方法
'Hi'.padEnd(10)        // 'Hi        '
'Hi'.padEnd(10, '.,*') // 'Hi.,*.,*.,'
'Hello'.padEnd(3, '*') // 'Hello' ←元の文字列より数字が小さいとき
```

これらは、ある文字列が第1引数で指定した長さになるまで第2引数の文字列を埋めます。第2引数がなければ空白文字で埋めます。`str.padStart()`と`str.padEnd()`の違いは埋める場所が元の文字列の左側か右側かの違いです。これは、とりあえず指定の文字数を作りたいときや、等幅フォントの環境下（コンソール出力など）で左寄せ／右寄せのレイアウトを作りたいときに便利です。

```js
'-'.repeat(20)    // '--------------------'
'HEY!'.repeat(3)  // 'HEY!HEY!HEY!'
'Hello'.repeat(0) // '' ←0なら空文字列
```

ある文字列を指定回数繰り返すこともできます。これは単に繰り返したい数を与えるだけなのでシンプルです。

## 文字列の端を取り除く

```js
const str = '  Hello, World!  '
str.trimStart() // 'Hello, World!  ' ← 左側のみ
str.trimEnd()   // '  Hello, World!' ← 右側のみ
str.trim()      // 'Hello, World!' ← 両端

'\t\nHello\r\n'.trim() // 'Hello' ←タブや改行も除かれる
```

文字列の端にあるホワイトスペースを取り除くことができます。CSVファイルから読み込んだ値の前処理に便利です。どちら側のものを取り除くかでメソッドが3つに分かれています。

「ホワイトスペース」の定義は結構複雑で、空白文字のみならずタブ（`\t`）や改行文字（`\n`）なども含まれます。

## 文字列の大小を変換する

```js
const str = 'Hello, World!'
str.toLowerCase()    // 'hello, world!'
str.toUpperCase()    // 'HELLO, WORLD!'

// 日本語には影響しない
'こんにちはHELLO'.toLowerCase() // 'こんにちはhello'
```

文字列の英字部分を小文字／大文字に変換できます。英字以外は影響を受けません。

```js
// トルコ語の例（トルコ語ではiの大文字はİで小文字はı）
'istanbul'.toLocaleUpperCase('tr-TR') // 'İSTANBUL'
'Istanbul'.toLocaleLowerCase('tr-TR') // 'ıstanbul'
// 参考
'istanbul'.toUpperCase() // 'ISTANBUL'
'Istanbul'.toLowerCase() // 'istanbul'
```

`toLocaleUpperCase`/`toLocaleLowerCase`を使えば、指定したロケール固有の大文字小文字に変換します。日本語には当てはまりませんが、例えばトルコ語の一部の文字で使えます。

# おわり

この夏押さえておきたいJavaScriptの文字列操作コレクションでした。

文字列はプログラミングに欠かせない主役級アイテムの1つ。だからこそ、鮮やかに使いこなせるとたくさんのシーンで重宝するはずです。

今回ご紹介した方法を自分の実装スタイルに取り込んでみて、シンプルできれい見えするコードを狙ってみましょう！

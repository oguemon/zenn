---
title: "ESLintのフォーマット系ルールの廃止など: Cybozu Frontend Weekly (2023-11-07号)"
emoji: "🚮"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの[おぐえもん（@oguemon_com）](https://x.com/oguemon_com)です。

# はじめに

サイボウズでは毎週火曜日にFrontend Weeklyという「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2023/11/07のFrontend Weeklyで取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## Deprecation of formatting rules

https://eslint.org/blog/2023/10/deprecating-formatting-rules/

2023/11/03リリースの[eslint v8.53.0](https://github.com/eslint/eslint/releases/tag/v8.53.0)からスタイルフォーマット系のルールがdeprecatedになりました。メンテナンスの負荷軽減が主な理由です。

本バージョンでは`array-bracket-newline`をはじめとする67のルールがdeprecatedの対象になっています。

## Jest v30.0.0-alpha.1

https://github.com/jestjs/jest/releases/tag/v30.0.0-alpha.1

Jestの次世代バージョン[v30.0.0-alpha.1](https://github.com/jestjs/jest/releases/tag/v30.0.0-alpha.1)がリリースされました。v30には、`mts`ファイルや`cts`ファイルのデフォルトサポートをはじめとする変更が含まれています。

## Astro 3.4: Page Partials

https://astro.build/blog/astro-340/

Astro 3.4がリリースされました。部分的なHTMLを返す実装が可能になるPage Partialsという機能や、開発者向けにコンポーネントの各種情報を表示するDev Overlayという実験的機能が追加されています。

## Announcing WinterJS

https://wasmer.io/posts/announcing-winterjs-service-workers

[WinterJS](https://wasmer.io/wasmer/winterjs)というJavaScript Service Workersサーバの紹介記事です。

Rustで実装されていること、JavaScriptの実行にFirefoxで利用されている[SpiderMonkey](https://spidermonkey.dev/)を用いていることなどが特徴です。

## The URL Pattern Standard

https://blog.whatwg.org/url-pattern-standard

URL PatternがLiving Standardに追加されたことを紹介する記事です。

URL Patternは、`/posts/*`や`/books/:id`のような記法でURLのパターンを表現する構文仕様です。この仕様は、DenoやCloudflare Workers、Next.js Edge Runtime、Netlify Functionsなどブラウザ以外でも既に採用されています。

## Remix ❤️ Vite | Remix

https://remix.run/blog/remix-heart-vite

RemixがViteのサポートを開始しました。現在はunstableな機能として提供されています。

記事中には、Viteのサポートを開始した経緯や理由などが記されています。

## Closure Library is in Maintenance Mode #1214

https://github.com/google/closure-library/issues/1214

Closure Libraryが11月1日からメンテナンスモードに入り、2024年8月に更新が終了されることになりました。2009年の初回リリースから14年の歴史に幕を閉じることになります。

現在のJavaScript開発における標準がClosure Libraryのアプローチに適合しておらず、"JavaScriptの書き方を改善する"というミッションをClosure Libraryが果たせなくなったことが理由として挙げられています。

## We have a working prototype and plan to release experimental support in the coming months.

https://github.com/storybookjs/storybook/issues/21540#issuecomment-1784953028

StoryBookにおいて、数ヶ月以内にReact Server Componentsが実験的にサポートされる予定であることが発表されました。

## Deno 1.38: HTML doc generator and HMR

https://deno.com/blog/v1.38

Deno 1.38がリリースされました。

作成したモジュールに対してドキュメントとして公開できるHTMLをコマンド1つで自動生成できるHTML doc generatorという機能などが追加されています。

## State of React 2023

https://survey.devographics.com/ja-JP/survey/state-of-react/2023

State of React 2023では、その名の通り2023年におけるReactの利用に関する各種統計調査を行っています。

調査期間は11月15日（水）までで、それまで開発者による回答を募集しています。

## Intent to Ship: `:has` Selector

https://groups.google.com/a/mozilla.org/g/dev-platform/c/oacuvZ2_hLg/m/4o28pFLkAwAJ

CSSのセレクタ`:has()`がFirefox121で実装される見込みです。

`:has()`は、指定したセレクタにマッチする要素を内側に最低1つ持つような要素を選択できるようにするセレクタです。Firefox121は、12月19日のリリースを予定しています。

## Alipay started its own Rust bundler project called Mako.

https://x.com/boshen_c/status/1719596594985681275

Alipay（支付宝）が、独自のRustバンドラープロジェクト**Mako**を始めました。

[元の動画](https://www.bilibili.com/video/BV15c411d7FZ/)によると、esbuildに次ぐパフォーマンスが計測されています。

## A new way to bring garbage collected programming languages efficiently to WebAssembly

https://v8.dev/blog/wasm-gc-porting

ガベージコレクションを備えたプログラミング言語をWebAssemblyで効率的にサポートする方法について技術的な解説を与えた記事です。

## Write a JavaScript Parser in Rust

https://oxc-project.github.io/javascript-parser-in-rust/ja/

RustでJavaScriptパーサーを書くためのガイドサイトです。

テキスト読み込みからASTの生成までの一連の流れを解説するとともに、それをRustで実装する上でのテクニックなどが紹介されています。

## The Set Theory

https://talks.antfu.me/2023/vuefesjapan/1

Vueなどの開発を手掛ける[Anthony Fu](https://antfu.me/)氏が[Vue Fes Japan 2023](https://vuefes.jp/2023/)で公演したときの資料が公開されました。

広いユーザーに利用されるOSSを作るために取り組んだことなどが紹介されています。

## ESLintのローカルルールで独自のコーディング規約を実装する

https://speakerdeck.com/berlysia/202311-lightning-techtalks-2

ESLintのFlat Config機能を活用することで独自のコーディング規約を簡単に実装できることを紹介する資料です。

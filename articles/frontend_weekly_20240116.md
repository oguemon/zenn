---
title: "サードパーティCookieがChromeユーザーの1%で制限など: Cybozu Frontend Weekly (2024-01-16号)"
emoji: "🎍"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

あけましておめでとうございます！サイボウズ株式会社フロントエンドエンジニアの[おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com)です。

# はじめに

サイボウズでは毎週火曜日にFrontend Weeklyという「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2024年1月16日のFrontend Weeklyで取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## React Aria Components v1 リリース

https://react-spectrum.adobe.com/releases/2023-12-20.html

Adobeは、React Aria Componentsをv1.0.0としてリリースしました。

React Ariaに関してはLPページも公開されており、サイト上でReact Aria Componentsを試してみることができます。

https://react-spectrum.adobe.com/react-aria/

## Chromeユーザーの1%に対して、デフォルトでサードパーティCookieの使用が制限されている

https://developers.google.com/privacy-sandbox/blog/cookie-countdown-2024jan?hl=ja

2024年1月4日から、表題の制限が開始されました。Chromeでは2024年後半に全てのユーザーのサードパーティCookieを段階的に廃止する予定です。

## ChromiumではPrefetchやPrerenderを総称してSpeculative Loadingと呼ぶことになった話

https://nhiroki.jp/2024/01/07/speculative-loading

今までChromiumではPrefetchやPrerenderを`Preloading`と総称していましたが、これを`Speculative Loading`に改めました。

`Preloading`という名称は、`<link rel=preload>`やService WorkerのNavigation Preloadなど、既に広く使われているのが主な変更理由であると述べられています。

## Release Version 23.2.0 · jsdom/jsdom

https://github.com/jsdom/jsdom/releases/tag/23.2.0

jsdomの23.2.0がリリースされました。CSSセレクタエンジンが`nwsapi`から`@asamuzakjp/dom-selector`に変更されたのが主な変更点です。新しいエンジンは多くの新しいセレクタをサポートしています。

## 2023 JavaScript Rising Stars

https://risingstars.js.org/2023/en

2023年の間でスター数が増加したリポジトリのランキングです。フロントエンドフレームワークではReact、htmx、Svelteが順にランクインしていました。

## Astro ゆく年くる年

https://zenn.dev/morinokami/articles/astro-2023-2024

Astroの2023に実装された機能や2024のロードマップのまとめです。記事によると2023年はリリースが2日に1回のペースで行われており、この1年間におけるAstroの開発が極めて活発だったことが分かります。

## Future of Storybook in 2024

https://storybook.js.org/blog/future-of-storybook-2024/

Storybookが2023年にやったことのまとめや2024年のロードマップです。AngularやSvelteといったReact以外のフレームワークへの対応に投資をすることなどが述べられています。

## We originally planned to open source the codebase this year, but it will be pushed to Q1 2024.

https://twitter.com/youyuxi/status/1741065178597536191

Evan Youが、自身の開発するモジュールバンドラRolldownのステータスに関して昨年末に言及しました。Rolldownは、当初は2023年中にOSS化する予定でしたが、大規模なリファクタリングを行うため2024年の1Qに延期するとのことです。

## Announcing Vue 3.4

https://blog.vuejs.org/posts/vue-3-4

Vue 3.4（コードネーム「🏀 Slam Dunk」）がリリースされました。本バージョンでは、SFC（単一ファイルコンポーネント）のビルドの改善や、ReactivitySystemの効率化、Reactivity Transformの完全な削除などが行われています。

## PR TIMES のフロントエンドを支える技術 2023

https://developers.prtimes.jp/2023/12/28/prtimes-frontend-stack-2023/

PR TIMESで進められているフロントエンド刷新の技術構成を紹介しています。パッケージ管理に`pnpm`、Lintに`XO`、VRTに`Lost Pixel`が採用されています。

## Release v0.4.0 - Beta 2 · solidjs/solid-start

https://github.com/solidjs/solid-start/releases/tag/v0.4.0

SolidJSのフレームワークSolidStartのv0.4.0-Beta2がリリースされました。任意の場所にデプロイできるWebサーバーを構築するためのフレームワークNitroを内部に組み込んだことなどが主な変更点です。

## eBPFを使った自動テストツール「Keploy」がすごい

https://zenn.dev/jambowrd/articles/3ee00f61c0b827

APIテストの自動化を支援するツール「Keploy」の紹介記事です。Keployを利用すると、eBPFを用いて特定の通信をキャプチャして、そこからテストデータを作成できます。

## Rust-Based JavaScript Linters: Fast, But No Typed Linting Right Now

https://www.joshuakgoldberg.com/blog/rust-based-javascript-linters-fast-but-no-typed-linting-right-now/?s=t

RustベースのLinterに関する2023年現在の状況を整理した記事です。RustベースのLinterが未だTypeScriptの型チェックに対応していない現状に対する取り組みなどが話題に含まれています。

## ESLint v9.0.0-alpha.1 released

https://eslint.org/blog/2024/01/eslint-v9.0.0-alpha.1-released/

ESLint v9.0.0のアルファ版がリリースされました。v9.0.0からはESLintの設定ファイルにFlat Configという記法が導入されるなど大きな変更が加わる予定です。

## 型を少し工夫して、より安全なコードへ

https://www.m3tech.blog/entry/2024/01/16/094541

TypeScriptで活用できる型テクニックがいくつか紹介されています。詳細な実例が添えられていて実用的な内容になっています。

## JSer.info 13周年: JavaScriptの情報源を整理する

https://jser.info/2024/01/16/jser-13th/

JavaScriptに関する情報を発信しているWebサイト「JSer.info」が13周年を迎えました。記事では、ドメイン別/GitHubレポジトリ別の紹介数を今昔で比較したり、13年間の継続を実現するための工夫が紹介されています。

サイボウズでは、Frontend Weeklyにてフロントエンドトピックのキャッチアップに当サイトを活用しており、さらに**JSer.info Sponsor**として支援をしています。

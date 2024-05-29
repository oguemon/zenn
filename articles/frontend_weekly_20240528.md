---
title: "Google I/O 2024で発表された10の最新情報など: Cybozu Frontend Weekly (2024-05-28号)"
emoji: "👩‍🏫"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: true
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの[おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com)です。

# はじめに

サイボウズでは毎週火曜日にFrontend Weeklyという「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2024年5月28日のFrontend Weeklyで取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## RFC: Initial CSS Level Categorization

https://github.com/CSS-Next/css-next/discussions/92

CSSの進化に伴い、CSS3という用語が混乱を招いているため、CSS4やCSS5といった新たな分類を導入しようとする提案です。

## Ship: Third-party Cookie Grace Period Opt-Out

https://groups.google.com/a/chromium.org/g/blink-dev/c/seEsJTZPnz8

サードパーティクッキーの廃止に伴い、サードパーティクッキーをロールアウトを制御できる仕組みを提供します。

## ウェブ プラットフォーム ダッシュボードのお知らせ

https://web.dev/blog/web-platform-dashboard?hl=ja

5/14のGoogle I/Oで発表されたウェブプラットフォームダッシュボードの紹介記事です。ウェブプラットフォームダッシュボードでは、近年に出たWebブラウザの新機能に対して各ブラウザがどれだけサポートしているか確認できます。

## Storybook Rsbuild is here! 🥳

https://x.com/rspack_dev/status/1791395182623264982

Storybook Rsbuildの登場を知らせるポストです。RspackとRsbuildに基づいて開発されており、Webpack版より5倍高速です。

https://github.com/rspack-contrib/storybook-rsbuild

## CVE-2024-4367 – Arbitrary JavaScript execution in PDF.js

https://codeanlabs.com/blog/research/cve-2024-4367-arbitrary-js-execution-in-pdf-js/

PDF.jsから脆弱性が検出されました。悪意のあるPDFファイルを開くと任意のJavaScriptコードが実行されます。Firefoxユーザー(<126)やPDF.jsを使用するアプリに影響します。

## Next.js 15 RC

https://nextjs.org/blog/next-15-rc

Next.js 15 RCの紹介記事です。React 19とReact Compilerが利用可能になる他。fetchやGETリクエストのキャッシュがデフォルトでオフになるなどの変更が加えられています。

## Introducing Pigment CSS: the next generation of CSS-in-JS

https://mui.com/blog/introducing-pigment-css/

[MUI](https://mui.com/)がゼロランタイムのCSS-in-JSライブラリ「Pigment CSS」のアルファ版を公開しました。React Server Componentsと互換性を保ちつつ、実行時パフォーマンスを改善しています。今年の後半に正式リリース予定です。

## Ship: CSS Anchor Positioning: anchor-scope

https://groups.google.com/a/chromium.org/g/blink-dev/c/D2-NxrsMKe4

`anchor-scope`プロパティを用いて、アンカー名の可視性を特定のサブツリーに限定する仕様です。これは、同一ページ上の複数のコンポーネントが干渉せずにアンカー位置を使用する上で重要になります。

## Chromium Blog: Advancing Our Amazing Bet on Asymmetric Cryptography

https://blog.chromium.org/2024/05/advancing-our-amazing-bet-on-asymmetric.html

Chrome124より、TLS 1.3とQUICに対して最新のKyberドラフト仕様をデフォルトで有効にしたことを知らせる記事です。既にいくつかの課題が上がっており、例えば鍵サイズやレイテンシの増加によるPKIの俊敏性への影響が課題になっています。

## Prototype: CHIPS(Cookies Having Independent Partitioned State)

https://groups.google.com/a/mozilla.org/g/dev-platform/c/7p3DC__Wgos

CHIPS（独立したパーティション状態を持つクッキー）を実装し、新しいクッキー属性「Partitioned」をサポート。これにより、ウェブサイトはパーティション化されたクッキーを使用でき、サードパーティークッキー廃止への対応が進みます。

## Next.jsのSSRF脆弱性 CVE-2024-34351

https://zenn.dev/akfm/articles/nextjs-ssrf-vulnerability

Next.jsのSSRF（=Server Side Request Forgery）脆弱性についての解説記事です。Next.js 14.1.0以下のセルフホスト環境を利用している場合に、Server Actionsで相対パスの`redirect`を実行するとSSRF脆弱性が発生する可能性があります。

## Google I/O 2024 で発表された 10 の最新情報: すべてのウェブ デベロッパーのために AI の力を活用

https://developer.chrome.com/blog/web-at-io24?hl=ja

Google I/O 2024における発表内容のまとめ記事です。Chrome DevToolsにAIを搭載する予定などが発表されました。

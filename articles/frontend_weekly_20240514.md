---
title: "フロントエンド開発者/技術者ハンドブック2024など: Cybozu Frontend Weekly (2024-05-14号)"
emoji: "🔰"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの[おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com)です。

# はじめに

サイボウズでは毎週火曜日にFrontend Weeklyという「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2024年5月14日のFrontend Weeklyで取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## The Front End Developer/Engineer Handbook 2024

https://frontendmasters.com/guides/front-end-handbook/2024

2024年のフロントエンド周辺の領域に関する解説を網羅的に扱ったドキュメントです。

## Libraries with issues #25

https://github.com/eps1lon/DefinitelyTyped/issues/25

Reactを取り巻く一部の周辺ライブラリで起票したReact19対応IssueをまとめたIssueです。

## JavaScript: 最初の 20 年

https://inzkyk.xyz/js_20_years/

Allen Wirfs-Brock, Brendan Eich著[JavaScript: the first 20 years](https://dl.acm.org/doi/10.1145/3386327)の翻訳ページです。

## JSR Is Not Another Package Manager

https://deno.com/blog/jsr-is-not-another-package-manager

npmパッケージ・レジストリがほとんど進化していない現状を指摘して、JSRが目指すところを表明した記事です。

## Node.js — Node.js 22 is now available!

https://nodejs.org/en/blog/announcements/v22-release-announce

近々リリースされるNode.js 22の新機能や変更点を紹介する記事です。`require()`を使ったESModuleの読み込みが一部条件下で可能になるなどの変更が加えられています。

## Bun v1.1.5 | Bun Blog

https://bun.sh/blog/bun-v1.1.5

Bun v1.1.5の新機能や変更点を紹介する記事です。クロスコンパイルのサポートなどが追加されています。

## May 1, 2024 Release

https://react-spectrum.adobe.com/releases/2024-05-01.html

React Ariaの5月のリリース内容をまとめた記事です。Submenu, DropZone, File Triggerなどが正式版になるなどの変更が加えられています。

## Creating a pointer-friendly submenu experience

https://react-spectrum.adobe.com/blog/creating-a-pointer-friendly-submenu-experience.html

メニューをホバーしているときにサブメニューが表示されるUIにおいて、ポインターの操作性を向上させるためのアプローチを紹介した記事です。ホバー範囲の工夫のみならず、ポインターの速度なども勘案されています。

## @headlessui/react@v2.0.0

https://github.com/tailwindlabs/headlessui/releases/tag/%40headlessui%2Freact%40v2.0.0

HeadlessUI@react v2.0の新機能や変更点を紹介する記事です。CheckboxやFormに関連するコンポーネントが追加されるなどの変更が加えられています。

## Intent to Ship: View Transitions Same-Origin Navigation

https://groups.google.com/a/chromium.org/g/blink-dev/c/LsA567xpe7k

Chromeにて、View TransitionがMPAでも利用できるようになりました。利用するには`viewTransition API for navigations`のフラグを有効化する必要があります。

## Intent to Prototype: Find-in-page highlight pseudos

https://groups.google.com/a/chromium.org/g/blink-dev/c/5FS_4mVQBLc

ページ内検索されてヒットした要素のスタイルを`::search-text`で変更できるようにする仕様です。

## Intent to Prototype: Multi-argument alt text in CSS Generated Content

https://groups.google.com/a/chromium.org/g/blink-dev/c/uCOrwnFuqNA

CSSのcontent属性で画像を指定したときに設定できるaltテキスト（例：`content: url("cat.jpg") / "A cute cat";`の`"A cute cat"`）に関数値を含む複数の引数値を指定できるようにする仕様です。

## Intent to Prototype and Ship: Align navigator.cookieEnabled with spec

https://groups.google.com/a/chromium.org/g/blink-dev/c/xU3gTW4aTfg

`navigator.cookieEnabled`の挙動を元の仕様に合わせる変更が行われます。今までは、3rd Party Cookie非推奨化に伴いパーティション化されていないクッキーへのアクセス可否を示していましたが、単にそのサイトでCookieが使用できるかどうかを返すようになります。

## Chromium Blog: How Machine Learning improved the Chrome address bar on Windows, Mac and ChromeOS

https://blog.chromium.org/2024/04/how-machine-learning-improved-chrome.html

Chrome 124からアドレスバー（omnibox）に入力を与えた時のサジェストに機械学習モデルが使用されることを紹介した記事です。

## Ship: navigator.clipboard.read() and navigator.clipboard.write()

https://groups.google.com/a/mozilla.org/g/dev-platform/c/lNXj_A-Lllk

クリップボード操作を行う`navigator.clipboard.read/write()`がFirefox127からデフォルトで利用できることに触れています。

## Ship: New Set Methods

https://groups.google.com/a/mozilla.org/g/dev-platform/c/MvkV6MI6dMs

[新しいSetメソッド](https://github.com/tc39/proposal-set-methods)がFirefox127からデフォルトで利用できることに触れています。

## Prototype: CSS Anchor Positioning

https://groups.google.com/a/mozilla.org/g/dev-platform/c/4cbytMKbHtg

[CSS Anchor Positioning](https://drafts.csswg.org/css-anchor-position-1/)に関して、SafariのWebKitは公式見解がないものの、仕様の共同編集はしていることに触れています。

## Google Chrome's new post-quantum cryptography may break TLS connections

https://www.bleepingcomputer.com/news/security/google-chromes-new-post-quantum-cryptography-may-break-tls-connections/

Chrome 124から耐量子暗号(Post-quantum cryptography)を使用したTLS通信が有効になったことを伝える記事です。

## Hey everyone, thank you for sharing some of the challenges with accessing pathname.

https://github.com/vercel/next.js/issues/43704#issuecomment-2090798307

Next.jsで、Server ComponentsやLayoutがURL/Pathnameにアクセスできない理由を記したIssueコメントです。共通レイアウトのレンダリングの都合によるものと説明されています。

## In a future React release, it's likely we'll patch the Date API during SSR and hydration to prevent mismatches.

https://twitter.com/acdlite/status/1785691330988986587

今後のReactのリリースにて、ReactのSSRとハイドレーションの間で生じるDate値のミスマッチを防ぐために、Date APIへパッチを適用することを検討している旨を知らせるツイートです。

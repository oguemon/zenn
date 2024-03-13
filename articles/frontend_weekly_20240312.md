---
title: "WebKit Features in Safari 17.4など: Cybozu Frontend Weekly (2024-03-12号)"
emoji: "🦁"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: true
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの[おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com)です。

# はじめに

サイボウズでは毎週火曜日にFrontend Weeklyという「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2024年3月12日のFrontend Weeklyで取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## WebKit Features in Safari 17.4

https://webkit.org/blog/15063/webkit-features-in-safari-17-4/

Safari 17.4で使用されるWebKitの新機能を紹介するページです。

アーキテクチャの改善をはじめ、多数の変更が含まれています。

## Readonly files in VSCode

https://www.stefanjudis.com/today-i-learned/readonly-files-in-vscode/

VSCodeの設定（`files.readonlyInclude`）で指定したパスのファイルをReadonlyにできる機能について紹介しています。

自動生成したファイルなど、人の手で編集されたくないファイルがある場合に便利です。

## Rolldown is now open source on GitHub

https://twitter.com/rolldown_rs/status/1766013359932297275

[Rolldown](https://rolldown.rs/)のオープンソース化を知らせるポストです。

Rolldownは、Rustで書かれたJavaScriptバンドラで、将来的に[Vite](https://ja.vitejs.dev/)で使用されることを目的としています。

## Add `React.useActionState` #28491

https://github.com/facebook/react/pull/28491

Reactに`useActionState`を追加するPull Requestです。

これは、ReactDOMにある`useFormState`を置き換えるために追加されたもので、フォームのペンディング状態を返す改善が加えられています。

## [WIP] module: support require()ing synchronous ESM graphs #51977

https://github.com/nodejs/node/pull/51977

Node.jsで、ESMに対する同期requireのサポートを提案するPRがDraft状態で用意されています。

## Simple setup: Virtual Screen Reader in Storybook

https://dev.to/scottnath/simple-setup-virtual-screen-reader-in-storybook-2efo

[Virtual Screen Reader](https://www.guidepup.dev/docs/virtual)とStorybookを利用したテストの手法を解説した記事です。これにより、スクリーンリーダーの読み上げ内容に関するテストを自動化できるようになります。

Virtual Screen Readerを提供しているスクリーンリーダーのドライバー・[Guidepup](https://www.guidepup.dev/)は、Playwrightなどと組み合わせることでVoiceOverなどのスクリーンリーダーを実際に操作することができます。

https://www.guidepup.dev/

## WinterJS 1.0

https://wasmer.io/posts/winterjs-v1

Wasmer Edge向けにコンパイル可能なJSランタイムのWinterJSのバージョン1.0がリリースされました。

WinterJSは、[WinterCG](https://wintercg.org/)のみならず、Cloudflare APIや既存の各種Webフレームワークとの互換性を謳っています。

## LAUNCH WEEK STARTS NOW!

https://twitter.com/astrodotbuild/status/1767294849848582202

[Astro](https://astro.build/)のLaunch Weekが開始されたことを伝えるポストです。

Launch Weekでは連日にわたりAstroに関するリリースが行われます。Astroの新バージョン[Astro 4.5](https://astro.build/blog/astro-450/)や、Astro DBなどのリリースが予告されています。

## Big things coming every day next week... 👀

https://twitter.com/prisma/status/1765801500368945223

[Prisma](https://www.prisma.io/)も3/11-15に亘ってLaunch Weekが開催されています。

月曜日は、Prisma Pulseのリリースが発表されました。

https://www.prisma.io/blog/prisma-pulse-in-general-availability

## JSON Canvas — An open file format for infinite canvas data.

https://jsoncanvas.org/

`canvas`で無限平面のUIを構築する時に利用できるデータフォーマットです。

JSON Canvasは、情報整理ツールの[Obsidian](https://obsidian.md/)で利用されています。

## App Store、Spotify、そして欧州の活気あるデジタル音楽市場

https://www.apple.com/jp/newsroom/2024/03/the-app-store-spotify-and-europes-thriving-digital-music-market/

App Storeがデジタル音楽市場における競争の障壁となっているとの主張を欧州委員会が決定したことを受けて、Appleが発表した声明です。

本決定の主な提唱者としてSpotifyを名指しして、同社のサービスの成功におけるApp Storeの寄与にも関わらず同社がAppleに対して何も支払っていないことなどを指摘し、あわせて欧州委員会の決定に対して上訴する旨を述べています。

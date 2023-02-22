---
title: "iOS16.4 beta1でWebアプリの通知に対応など : Cybozu Frontend Weekly (2023-02-21号)" # 目立ったニュースを選ぶ
emoji: "🔔" # お好きな絵文字を
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは! サイボウズ株式会社フロントエンドエンジニアの [おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com) です。

# はじめに

サイボウズ社内では毎週火曜日に Frontend Weekly と題し「一週間の間にあったフロントエンドニュースを共有する会」を開催しています。

今回は、2023/02/21 の Frontend Weekly で取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## Remixing Hydrogen

https://hydrogen.shopify.dev/updates

Shopify 社が開発したコンポーネントライブラリ [Hydrogen](https://hydrogen.shopify.dev/) が、同社が手がける Web フレームワーク [Remix](https://remix.run/) との連携をより強化することを表明しています。

Shopify 社は、Remix を手掛けていた Remix 社を[2022 年に買収して](https://remix.run/blog/remixing-shopify)おり、自社のプロダクトとの連携を通じてより良い EC サイトの開発に繋がる環境整備を進めています。

## WebContainer API is here.

https://blog.stackblitz.com/posts/webcontainer-api-is-here/

2 月 14 日、[Web Container](https://webcontainers.io/) の API が公開されました。Web Container は WebAssembly ベースのランタイムで、ブラウザの処理によって Node.js を動かすことができます。

ローカルで環境構築をしなくともサーバサイドライブラリ等を簡単に試すことができることから、社内ではチュートリアル用途での利用の拡大が期待されていました。

実際、Web Container は既に[Svelte のチュートリアル](https://learn.svelte.dev/tutorial/welcome-to-svelte)で活用されています。

## Announcing Sandpack 2.0 and a Node.js runtime for any browser

https://codesandbox.io/blog/announcing-sandpack-2

WebContainer API 公開の 2 日後にあたる 2 月 16 日、CodeSandbox 社はブラウザ上で Node.js のサーバサイドコードが動作するランタイム Sandpack 2.0 を公開しました！

記事の文中では、Sandpack 2.0 の実例として Node.js や Next.js などを用いたサーバサイドコードが埋め込まれており、実際にブラウザ上で動作することを確かめられます。

前述した WebContainers と違って、モダンブラウザの技術を使わずに実装されているため、iOS のブラウザなどでも動作するのが特長です。一方で、メモリ消費に対する懸念から Node API に完全対応しているわけでない点に留意が必要です。

## Firefox 110.0, See All New Features, Updates and Fixes

https://www.mozilla.org/en-US/firefox/110.0/releasenotes/

2 月 14 日にリリースされた Firefox 110.0 にて、CSS の [Container queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Container_Queries) がサポートされました！

Container queries は、コンテナと呼ばれる特定の要素のサイズに応じて要素のスタイリングを条件分けできる記法で、レスポンシブデザインの実装方法に革新をもたらす可能性を秘めています。

Firefox の対応により、全ての主要ブラウザで Container queries を利用できるようになりました。Container queries の時代の到来を予感させます。

## Web Push for Web Apps on iOS and iPadOS

https://webkit.org/blog/13878/web-push-for-web-apps-on-ios-and-ipados/

2 月 16 日に公開された iOS/iPadOS 16.4 beta 1 にて、ホーム画面に追加した Web アプリ（PWA）からプッシュ通知ができるようになりました！

iPhone/iPad においてモバイルアプリの専売特許だった通知機能が Web アプリでも実現可能になることで PWA の導入が加速することを期待する声が社内からあがりました。

## 「Safari 16.4 Beta リリース。盛りだくさんなので、ピックアップしていく」

https://twitter.com/azu_re/status/1627303346469240833

前項に関連する、Safari 16.4 Beta のリリースノート解説 Tweet です。[JSerInfo](https://jser.info/) の運営などで知られる[azu](https://twitter.com/azu_re)さんにより投稿されました。主な新機能がスレッドの中で紹介されています。

[リリースノート原文](https://developer.apple.com/documentation/safari-release-notes/safari-16_4-release-notes)を見ても分かるように、本更新は非常に多くの機能追加を含んでおり、社内でも大きな期待が寄せられてました。

## 2022/02/13〜2023/02/19 の最新情報 | 週刊 Deno

https://uki00a.github.io/deno-weekly/articles/2023/02/19

Node.js の開発者 Ryan Dahl さんが手がける JS/TS ランタイム[Deno](https://deno.land/)の最新情報が週次で公開されるサイトです。

Deno のレポジトリの Issue や Pull Request などに基づくニュースが平易な日本語で書かれており、英語が苦手な方でも Deno の動向を容易にキャッチアップできます！

今週は、`deno_std/node` が Deno 本体に組み込まれたという変更が報じられていました。内部 API の活用や、Node.js 互換レイヤーの Rust 化の予定を受けて、パフォーマンスの向上を期待する声が社内からあがりました。

## 「A super early Stage 0 proposal by @threepointone to add a built-in assertion function to JavaScript 🎉」

https://twitter.com/robpalmer2/status/1627281404324192256?s=20

https://github.com/threepointone/proposal-error-assert

ECMAScript で`Error.assert(condition, message);`を利用できるようにする提案が、ECMAScript の仕様を決める委員会 [TC39](https://tc39.es/) において Stage 0 (strawperson)に加えられました。

`Error.assert()`はコードの安全性などに寄与するメソッドで、TypeScript などでは類似するものが既に実装されています。

仕様策定までのステージは、0(strawperson)〜4(maturity)の 5 段階あり、実現までの道のりは決して短くありませんが、今後の動向に要注目です。

## State of React Native

https://results.stateofreactnative.com

モバイルアプリフレームワーク React Native の利用状況に関する統計をまとめたサイトです。

[The State of CSS](https://2022.stateofcss.com/ja-jp/)や[The State of JS](https://2022.stateofjs.com/ja-jp/)のように、使用されている機能や開発者の実態などがグラフィカルにまとめられています。

[React Native 利用者の出自は、React 利用者がモバイルアプリエンジニア（iOS/Android）の 2 倍以上におよぶ](https://results.stateofreactnative.com/developer-background/)など、興味深い結果が数多く並んでいました。

## The IE11 desktop application is permanently disabled beginning today, February 14, 2023

https://learn.microsoft.com/en-us/windows/release-health/windows-message-center#3014

2 月 14 日の Edge アップデートにより、Internet Explorer 11（IE11） が恒久無効化されました。今後 IE11 の`exe`ファイルを実行しても、Edge に強制リダイレクトされて IE11 が開けません。

IE11 は、2022 年 6 月 15 日に Windows 10 におけるサポートが終了し、約 27 年にわたる歴史に終止符が打たれました。今回の処置はサポート終了後の事後処理の一環です。

マイクロソフト社は、今後、6 月 13 日の更新でスタートメニューやタスクバーのアイコンを取り除くことを公表しています。

社内では多くの者が IE との別れを偲んでいました。

## Try out CSS Nesting today

https://webkit.org/blog/13813/try-css-nesting-today-in-safari-technology-preview/

CSS で[Sass](https://sass-lang.com/)のようなネスト記法が利用できる CSS Nesting が Safari に導入されつつあることを報じた記事です。

CSS Nesting は、執筆時点では Google Chrome しか対応しておらず、もし Safari で実装されれば 2 例目になります。

## 「Vercel Cron Jobs. Next week.」

https://twitter.com/leeerob/status/1625249090932994051

Vercel の Serverless Function を用いて Cron の実行ができるようになることを予告する Tweet です。

今まで、バッチ処理の実行のためにサーバーを別途用意する必要があったので、それが不要になることによる利便性の向上に社内から期待の声があがっていました。

## Why I like Rich Harris by baseballyama

https://docs.google.com/presentation/d/16GCSVB-h_TlZtyq-CQ98_fUux5fpKy8QCybMsgH4SsI/edit#slide=id.g1f2376c7dc7_1_56

2 月 19 日に開催された [Vercel Meetup](https://vercel.connpass.com/event/274772/) における[baseballyama](https://twitter.com/baseballyama_)さんの登壇資料です。

本資料は、Web フレームワーク Svelte の開発者である Rich Harris さんの好きなところをテーマに掲げていますが、資料の中には日本国内における Svelte、SvelteKit の採用事例がまとまっており、非常に興味深いデータが揃っています。

## Popover API - JavaScript 不要、HTML のみでポップオーバー UI

https://zenn.dev/yusukehirao/articles/popover-api-and-attributes

HTML の仕様である HTML Living Standard に取り込まれた新仕様 [Popover API](https://momdo.github.io/html/popover.html) の解説記事です。

Popover API はまだ実装されているブラウザが僅かですが、`popover`属性や`popovertoggletarget`属性を利用することで簡単にポップオーバーを作成できるという大きな利便性を有しています。

Frontend Weekly では、この仕様の内容に加えて、[新仕様の起案](https://github.com/whatwg/html/issues/7785)〜[仕様への取り込み](https://github.com/whatwg/html/pull/8221)（WHATWG が管理するレポジトリへのマージ）の一連の流れを追いました。

## TanStack Start

https://twitter.com/TkDodo/status/1625779824223551489

[TanStack Query](https://tanstack.com/query/) などのライブラリで知られる TanStack 社が、新たなライブラリとして TanStack Start というものを準備していることが明らかになりました。

TanStack Start は、SSR フレンドリーで、かつ型安全なフレームワークを謳っており、今後明らかになるであろう具体的な内容に期待が寄せられていました。

## [Watch This Space] Angular Reactivity with Signals #49090

https://github.com/angular/angular/discussions/49090

Angular が Signals の機能を追加するためのプロトタイプを始めたようです。RFC の公開は進捗によるとしつつも現時点で 2023 年末を予定しています。

Signals の構想にあたって、SolidJS などを手掛けている [Ryan Carniato](https://twitter.com/RyanCarniato) さんから多くのことを教えてもらったと文中に書かれており、主要 OSS 間の交流が垣間見えます。

## Release v1.13.0 · remix-run/remix

https://github.com/remix-run/remix/releases/tag/remix%401.13.0

Remix の v1.13.0 で [PostCSS](https://postcss.org/) と [Tailwind CSS](https://tailwindcss.com/) がサポートされました。

導入のためのフラグに`unstable_postcss`や`unstable_tailwind`という名称がついていることから、まだ安定版ではないようです。

## Introducing Qwik City Server Functions

https://www.builder.io/blog/qwik-city-server-functions

2022 年にリリースされた Web フレームワーク [Qwik](https://qwik.builder.io/) におけるサーバサイド関数の記法を紹介した記事です。

サーバサイド関数（Next.js でいう`getSeverSideProps`や、Remix でいう`loader`）は、Qwik では`loader$` という名前で定義されています。この記事では、`loader$`は型安全な上、どこでも定義できる、どのファイルからも参照できるなど、Next.js などの既存フレームワークに対する一種の優位性が謳われています。

## Vue 経験者向け Vue3 スタートガイド [実行環境付き]

https://zenn.dev/ryo_kawamata/articles/vue3-upgrade-guide

Vue 3 で新たに追加された API や構文が紹介されている記事です。

Codesandbox による実装例がひとつひとつ添えられており、実装とその挙動を確かめながら読み進めることができる丁寧な作りになっています。Vue をゴリゴリ書く方だけでなく、教養的に内容を知りたい方にとっても役立つ内容です！

## 「Announcing AI Commits – a CLI tool that generates your commit message for you with AI. Available on npm today!」

https://twitter.com/nutlope/status/1625311440696446976

2 月 14 日、[AI Commits](https://www.npmjs.com/package/aicommits)という npm パッケージが公開されました。

AI Commits を使うと、ファイルの変更差分に基づいて、そのコミットメッセージを自動で生成することができます。

自動生成の処理には、ChatGPT などのサービスで知られる OpenAI 社の API が利用されており、近頃話題になっている高度な自然言語 AI モデルの一種の応用例とも言えます。

## ブラウザ拡張機能を作るための React フレームワーク『Plasmo』

https://zenn.dev/nado1001/articles/plasmo-browser-extension

ブラウザ拡張機能開発のフレームワーク[plasmo](https://www.plasmo.com/)の紹介記事です。

plasmo は、React や Typescript をサポートしており、フロントエンド開発の技術スタックに近い形でブラウザ拡張機能を開発することができます。フロントエンドエンジニアによるブラウザ拡張開発機能の敷居が下がることが期待されています。

## Speculation Rules API によるプリレンダリングのためのメトリクス設計

https://nhiroki.jp/2023/02/13/metrics-for-prerendering

プリレンダリング時を用いているサイトにおいて、 [LCP](https://web.dev/i18n/ja/lcp/) を正確に計測するのは決して容易なことではありません。

そこで、この記事では、 Resource Timing API に追加された `activationStart` について述べつつ、プリレンダリングにおけるメトリクスの取り方について解説しています。

# あとがき

個人的には、iOS/iPadOS の Safari における通知対応の記事に心を持っていかれた回でした。モバイル端末において Web アプリケーションがますます活躍する未来に期待ですね！

フロントエンドエキスパートチームでは毎月、最終火曜日の 17 時から Frontend Monthly というイベントを Youtube Live で開催しています。その月のフロントエンド注目ニュースやゲストを呼んでの対談などフロントエンドに関する発信していますので是非どうぞ！

https://www.youtube.com/playlist?list=PLPTndynQK4dxLZFEZgOZjt_zKG-0JWoWy

またフロントエンドエキスパートチームでは、一緒にサイボウズのフロントエンドを最高にする仲間を募集しています。興味ある方はこちら ↓ から！

https://cybozu.github.io/frontend-expert/

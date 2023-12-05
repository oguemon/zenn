---
title: "State of JavaScript 2023の回答募集中など: Cybozu Frontend Weekly (2023-12-05号)"
emoji: "👩‍💻"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの[おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com)です。

# はじめに

サイボウズでは毎週火曜日にFrontend Weeklyという「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2023年12月5日のFrontend Weeklyで取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## Ark UI

https://ark-ui.com/

ChakraがリリースしているUIコンポーネントのヘッドレスライブラリです。11/9にv1.0.0がリリースされました。

Ark UIはReactやVueなどの主要フレームワークで利用できます。

## State of JavaScript 2023

https://survey.devographics.com/ja-JP/survey/state-of-js/2023

JavaScript近辺の技術の理解/利用を調査するState of JavaScript 2023が現在回答を募集しています。

回答期間は11/22〜12/12で、その後速やかに集計結果が公表されます。

## Biome formatter wins the Prettier challenge

https://biomejs.dev/blog/biome-wins-prettier-challenge/

Prettierが募集していた[Rust製JSフォーマッター実装チャレンジ](https://console.algora.io/challenges/prettier)で、Biome formatterが賞金（25,000米ドル）を獲得しました。

Biome formatterは、JavaScriptとTypeScript、JSXにおいてPrettierに対して96%を超える互換性を実現しました。

## Astro 4.0 Beta Release

https://astro.build/blog/astro-4-beta/

11/27にAstro 4.0のBeta版がリリースされました。

今回の更新はVite 5対応の他、いくつかの実験的機能がstable化される予定です。

## feTS

https://the-guild.dev/openapi/fets

feTSは、Client/Server間の通信を型安全にすることを可能にするTypeScriptファーストなHTTPフレームワークです。

OpenAPIの仕様とJSON Schemaを駆使して型を推論することでコード生成を不要にしているのが特長です。

## Explicit Resource Management: Exploring JavaScript's and TypeScript's new feature

https://iliazeus.github.io/articles/js-explicit-resource-management-en/

TypeScript 5.2で追加された新機能であるExplicit Resource Management（`using`宣言）の実装方法を解説する記事です。

利用事例に応じたサンプルが多数用意されており、実際の使い方がイメージしやすくなっています。

## Introducing Support for Hosting Any SSR app on AWS Amplify Hosting

https://aws.amazon.com/jp/blogs/mobile/introducing-support-for-hosting-any-ssr-app-on-aws-amplify-hosting/

AWS Amplify Hostingが、Next.js以外（Nuxt、Svelte Kitなど）のフレームワークを用いたSSRアプリケーションをサポートしました。

記事では、SSRアプリケーションのデプロイ方法についても触れています。

## perf: Reduce object generation and optimize performance. #95

https://github.com/honojs/node-server/pull/95

Honoにおいて、Node.js上で3倍近く速くなるプルリクエストがマージされました。

https://twitter.com/usualoma/status/1729071315632697558

ポストにあるように、`Request`/`Response`オブジェクトに潜んでいたボトルネックにアプローチしたことで、パフォーマンスが改善されたようです。

## Prettier's CLI: A Performance Deep Dive

https://prettier.io/blog/2023/11/30/cli-deep-dive

Prettier CLIにおけるパフォーマンス改善の取り組みを紹介した記事です。

ファイル探索の高速化、設定ファイルの読み込みの高速化、キャッシュ戦略などの様々な観点での取り組みが述べられています。

## ESLint の Suggestions から学ぶ、コードの自動修正の奥深さ

https://www.mizdra.net/entry/2023/12/04/093000

JavaScript向けのLinter「ESLint」を例として、コードの自動修正機能の複雑さを解説する記事です。

ESLintではコードの誤りに対してfixableか（機械的な修正が可能か）否かという分類をしていて、fixableでない誤りについてもSuggestionsという機能を用いてユーザーに対して修正の提案を実施しています。

## Vue & Vite Rustify

https://speakerdeck.com/kazupon/vue-and-vite-rustify

11/7および12/3に開かれたVue Fes Japan 2023の報告会で発表された資料です。

Vue Fes Japan 2023の振り返りに加えて、近年のツールチェーンの動向についても解説されています。

## TypeScriptを他のツールで取り扱うためのコンパイラオプションについて

https://qiita.com/uhyo/items/c33489155e1817479948

TypeScriptのビルドパイプラインに`tsc`以外のツールを含める際に使用されるコンパイラオプションである`isolatedModules`や`verbatimModuleSyntax`および現在提案中の`isolatedDeclarations`オプションについて詳説した記事です。

## Vitest 1.0 is here!

https://github.com/vitest-dev/vitest/releases/tag/v1.0.0

12/5にVitest 1.0がリリースされました。

本バージョンではNode.js 18とVite 5が必須になり、その他にもスナップショットがより視覚的に取得できるようになるなどの変更が加えられています。

## Storybook 7.6

https://storybook.js.org/blog/storybook-7-6/

11/28にStorybook 7.6がリリースされました。

SWCサポートを強化したことによるWebpackプロジェクトの高速化、StorybookのTest modeビルドの追加、アドオンの依存性をチェックする`storybook-doctor`コマンドの追加といった機能追加が行われています。

## Intent to ship: Popover Attribute

https://groups.google.com/a/mozilla.org/g/dev-platform/c/hrCP5RBO7mA/m/7w-1OsmbAQAJ

Firefox 122にて、Popover APIがデフォルトで使えるようになる予定です。

もしFirefoxで実装されたら、主要なブラウザ全てで本APIが使えるようになります。

## React 19 coming soon.

https://twitter.com/acdlite/status/1719474730363662473

React開発者の一人であるAndrew Clark氏が、React 19のリリースについて言及しています。

React 19にて現在の非推奨機能を削除することを仄めかしています。

---
title: "パフォーマンスパネルでパフォーマンスパネルを400%高速化など: Cybozu Frontend Weekly (2024-02-20号)"
emoji: "🚀"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの[おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com)です。

# はじめに

サイボウズでは毎週火曜日にFrontend Weeklyという「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2024年2月20日のFrontend Weeklyで取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## NGINXのコア開発者が親会社と決別、新たに「freenginx」という名前でフォーク版を作成開始

https://gigazine.net/news/20240215-freenginx/

NGINXの主要開発者の1人であるMaxim Dounin氏は、NGINXを所有するF5 Networks社との関係を解消し、新たにfreenginxという名前でフォーク版を作成することを発表しました。

freenginxの開発は、企業の恣意的行動から解放されることを目指しているようです。

## React Labs: What We've Been Working On – February 2024

https://react.dev/blog/2024/02/15/react-labs-what-we-have-been-working-on-february-2024

Reactが研究開発中のプロジェクトについて2024年2月時点の状況を発信しています。

メモ化の自動化などの機能を盛り込んだReact Compilerの現状や、React Canariesにおける新機能などが紹介されています。

## Introducing SafeTest: A Novel Approach to Front End Testing

https://netflixtechblog.com/introducing-safetest-a-novel-approach-to-front-end-testing-37f9f88c152d

Netflixが開発した新しいテストツール[SafeTest](https://github.com/kolodny/safetest)の紹介記事です。

当ツールはWebアプリケーションのUIテストを行うためのもので、従来のUIテストを構成していたIntegrationテストとE2Eテストの長所を共に取り入れたものになっていると謳っています。

## UI = f(statesⁿ)

https://daverupert.com/2024/02/ui-states/

「UIは状態（State）の関数である」という考え方をより深掘りして、UIに影響を与える状態にどんなものがあるのかを考察して列挙した記事です。

## We're super excited to share that this dream is becoming a reality!

https://twitter.com/MUI_hq/status/1758326356356530407

MUIがBase UIのv1のリリースに向けた開発が進行している旨を伝えるポストです。

Base UIは、Material UIと違ってスタイルを持たないUIコンポーネントとhooksを提供するのが特長です。

## AWS、高速起動にこだわった軽量なJavaScriptランタイム「LLRT」（Low Latency Runtime）をオープンソースで公開。AWS Lambdaでの利用にフォーカス

https://www.publickey1.jp/blog/24/awsjavascriptllrtlow_latency_runtimeaws_lambda.html

Amazon Web Services（AWS）が、サーバレス環境AWS Lambdaでの使用にフォーカスしたJavaScriptランタイムLLRT（Low Latency Runtime）を公開しました。

高速起動を実現するため、ランタイムのサイズを軽量化している点が特長です。

## You can download @remix_run with stable @vite_js support now in the 2.7 prerelease! (2.7.0-pre.0)

https://x.com/pcattori/status/1758565176716964312

Remix v2.7のプレリリース（`2.7.0-pre.0`）で、Viteサポートの機能がStableになることを伝えるポストです。

[公式ドキュメント](https://remix.run/docs/en/release-next/future/vite)によると、Viteは将来的にはRemixのデフォルトコンパイラになる予定です。

## パフォーマンスに関するパネル表示でパフォーマンスパネルを400%高速化

https://developer.chrome.com/blog/perf-panel-4x-faster

GoogleがChromeのDevToolsにある[パフォーマンス]パネルに改善を加えて高速化を実現した旨を紹介しています。

[パフォーマンス]パネルの改善にあたっては、同じく[パフォーマンス]パネルの利用が役立ったそうです。

## Remove "use client" and mark packages as client-only instead #5826

https://github.com/adobe/react-spectrum/pull/5826

UIライブラリのReactコンポーネントにまとめて`"use client"`を付与することに関連したIssues/PRが一部のUIライブラリで上がっています。

例えば、現状のNext.jsでは、コンポーネントをBarrel Fileとして提供する場合に、Tree Shakingが不十分になりバンドルサイズが無用に増える可能性があるなどの問題点が指摘されています。

## Tappy

https://tappy.yahoo.co.jp/

LINEヤフー研究所が公開しているWebサービスです。

フォームにURLを入力するだけで、そのURL上にあるボタンやリンクを自動的に抽出し、それぞれの大きさや形状によりタップしやすさを「タップ成功率」という客観的な指標として評価してくれます。

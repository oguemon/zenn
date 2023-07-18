---
title: "日経電子版での自作SSRフレームワーク基盤についてなど: Cybozu Frontend Weekly (2023-07-18号)"
emoji: "📰"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの [おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com) です。

# はじめに

サイボウズでは毎週火曜日に Frontend Weekly という「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2023/07/18 の Frontend Weekly で取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## 日経電子版での自作 SSR フレームワーク基盤について — HACK The Nikkei

https://hack.nikkei.com/blog/denshiban-ssr/

[日経新聞社](https://www.nikkei.com/)が日経電子版で使っている独自 SSR フレームワークの紹介記事です。

この記事では、SSR フレームワークを自社開発している理由、どのようにして実装しているのかなどに触れています。

メディアサイトの特性や既存の構成などを考慮した検討、自作する上での課題などが述べられています。

## Prisma 5.0.0

https://github.com/prisma/prisma/releases/tag/5.0.0

Node.js & TypeScript を用いた ORM(Object-Relational Mapping)である[Prisma](https://www.prisma.io/)がメジャーアップデートしました。

https://www.prisma.io/blog/prisma-5-f66prwkjx72s

Prisma 5 では、Prisma のパフォーマンス向上を図るため、Prisma Client と Query Engine の間の通信プロトコルを GraphQL ベースから JSON ベースに変更するなどの改良が加えられています。

## Chrome Supports SolidJS in Building a Performant Web

https://www.solidjs.com/blog/chrome-supports-solidjs

高いパフォーマンスが特徴の UI フレームワーク[Solid.js](https://www.solidjs.com/) が、Aurora プロジェクト を通じて Chrome チームから 30,000 ドルの資金援助を受けました。

[Aurora](https://developer.chrome.com/aurora/)とは、Web 体験の向上に寄与する OSS プロジェクトと Chrome とのコラボレーションプロジェクトです。

この資金援助を通じて、Core Web Vitals の向上を実現するために Solid.js が手がけている技術開発を継続的に進めていくようです。

## Standards Positions

https://webkit.org/standards-positions/

HTML レンダリングエンジン [WebKit](https://webkit.org/) が、現在提案・策定された Web 仕様に対してどのポジション取っているのかを一覧で確認できるページです。

ポジションには、`support`（支持）と`oppose`（反対）、`neutral`（中立）があります。

ある仕様が WebKit で実装される見込みがあるかどうか調べるのに使えそうです。

## A case study on scroll-driven animations performance

https://developer.chrome.com/blog/scroll-animation-performance-case-study/

Chrome115 で新しく登場した、スクロール駆動のアニメーションを実現するための CSS プロパティ`animation-timeline` と JavaScript クラス`ScrollTimeline` の紹介記事です。

これらを用いると、あるコンテンツのスクロール量に応じたアニメーションを実装できます。

従来のスクロールイベントを用いた制御と異なり、メインスレッドへの負担を抑えることができるので、よりスムーズな動作を期待できます。

## npm package aws-sdk has been tested and works on Deno

https://twitter.com/deno_land/status/1681010475168043009

JavaScript/TypeScript ランタイム[Deno](https://deno.land/)で[`aws-sdk`パッケージ](https://www.npmjs.com/package/aws-sdk)を動かせるようになりました。

Deno と npm / Node.js の互換性向上が続いており、Deno の用途が拡がっています。

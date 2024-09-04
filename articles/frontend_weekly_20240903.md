---
title: "TypeScript 5.6の更新点など: Cybozu Frontend Weekly (2024-09-03号)"
emoji: "🆙"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの[おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com)です。

# はじめに

サイボウズでは毎週火曜日にFrontend Weeklyという「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2024年9月3日のFrontend Weeklyで取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## Nuxt Bridge を活用して Nuxt 3 へ移行しました

https://product.st.inc/entry/2024/08/21/141549

ネットショップサービス・[STORES](https://stores.jp/)がNuxt 3への移行を完了した旨を報告する記事です。[2022年12月の報告](https://product.st.inc/entry/2022/12/11/112330)の続編になります。

刷新における工夫点や、移行により得られた恩恵などが紹介されています。

## Announcing TypeScript 5.6 RC

https://devblogs.microsoft.com/typescript/announcing-typescript-5-6-rc/

TypeScript 5.6でリリース予定の新機能が紹介されています。

例えば、if文の条件文が常に`true`/`false`のときにその旨を指摘する機能（Disallowed Nullish and Truthy Checks）などが追加予定です。

## Material UI v6 is out now 🎉

https://mui.com/blog/material-ui-v6-is-out/

初コミットから10周年を迎えたReact UIコンポーネントライブラリ・[Material UI](https://github.com/mui/material-ui)がv6をリリースしたことを告知する記事です。

v6では、CSS theme variablesやカラースキーマのサポートなどが加わっています。

## Announcing TypedSQL: Make your raw SQL queries type-safe with Prisma ORM

https://www.prisma.io/blog/announcing-typedsql-make-your-raw-sql-queries-type-safe-with-prisma-orm

オブジェクト関係マッピング（ORM）ライブラリ・[Prisma ORM](https://www.prisma.io/orm)に追加された新機能・TypedSQLを紹介する記事です。

TypedSQLの特長は、SQL文を型安全に書くことができる点です。`.sql`ファイルに書いたSQLクエリがJSコードに変換されることで、クエリ結果や引数への型付けが可能になっているようです。

## Component testing in Storybook

https://storybook.js.org/blog/component-testing/

UI描画ツール・[Storybook](https://storybook.js.org/)を用いたコンポーネントテストの方法について紹介する記事です。

コンポーネントテストの方法のみならず、E2Eテストに対するパフォーマンス上の優位性なども述べられています。

## How to make your web page faster before it even loads

https://blog.sentry.io/how-to-make-your-web-page-faster-before-it-even-loads/

Time to first byte（TTFB）よりも前のイベントをどのように計測するか、そしてそれを改善に繋げる方法を[Sentry Trace View](https://docs.sentry.io/concepts/key-terms/tracing/trace-view/)を用いて解説する記事です。

Webページがロードされるまでの過程や、ロードを早くするために役立つヒントもあわせて紹介されています。

## Announcing Rspack 1.0

https://rspack.dev/blog/announcing-1-0

Rust製のJavaScriptバンドラ・[Rspack](https://rspack.dev/)のv1リリースを告知する記事です。

Rspackの現時点の利用者数・導入企業の紹介、v1の変更点（パフォーマンス・互換性向上など）、今後の開発予定などが記載されています。

## Astro 4.15

https://astro.build/blog/astro-4150/

フロントエンドフレームワーク・[Astro](https://astro.build/)のv4.15リリースを告知する記事です。

サーバーサイドの関数を型安全に定義・呼び出しできる機能・Astro ActionsのStable化などの変更が行われています。

## Next.js Conf is here. Join us in SF or online Oct 24.

https://x.com/nextjs/status/1828125586482430262

[Next.js Conf](https://nextjs.org/conf)が10月24日に開催される予定を知らせる投稿です。

CFPの募集も行われています。

https://x.com/nextjs/status/1829620358066106706

## Node.js Takes Steps Towards Removing Corepack

https://socket.dev/blog/node-js-takes-steps-towards-removing-corepack

[Node.js](https://nodejs.org/en)のPackage Maintenance Working Group（PMWG）が、[Corepack](https://github.com/nodejs/corepack)を最終的にNode.jsの配布から削除する計画を発表した記事です。

[Corepackを削除するPR](https://github.com/nodejs/node/pull/51981)には70を超えるコメントが寄せられ最終的にロックされるなど、削除の是非について物議を醸しています。

## Google Chrome 16周年

https://x.com/googlejapan/status/1830380112505655663

9/2にGoogle Chromeがリリースから16周年を迎えたことを祝福する投稿です。

同アカウントでは、Google Chromeが過去に使用していた懐かしのロゴも紹介しています。

https://x.com/googlejapan/status/1830546209443877055

https://x.com/googlejapan/status/1830017726221324517
---
title: "Bun 1.0のリリースなど: Cybozu Frontend Weekly (2023-09-12号)"
emoji: "🧄"
type: "tech"
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの[おぐえもん（@oguemon_com）](https://x.com/oguemon_com)です。

# はじめに

サイボウズでは毎週火曜日にFrontend Weeklyという「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2023/09/12のFrontend Weeklyで取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## Announcing native npm support on Deno Deploy

https://deno.com/blog/npm-on-deno-deploy

[Deno Deploy](https://deno.com/deploy)で、`npm:`記法を用いたnpmモジュールの実行がネイティブでサポートされました。これにより、npmモジュールを用いたアプリケーションのデプロイに際して必要だったビルド・バンドルのステップが不要になり、開発体験の向上を期待できます。

## Turbo 8 is dropping TypeScript

https://world.hey.com/dhh/turbo-8-is-dropping-typescript-70165c01

Ruby on Railsに標準搭載されているフレームワーク[Turbo](https://turbo.hotwired.dev/)の次世代バージョン8のコードベースからTypeScriptが削除されました。

> because it pollutes the code with type gymnastics that add ever so little joy to my development experience, and quite frequently considerable grief.

とあるように、型を書くことのコストパフォーマンスに対する不満が一因のようです。

## "In practice, hard to say who'll be dominant."

https://x.com/JoshuaKGoldberg/status/1699802456404677104

[typescript-eslint](https://typescript-eslint.io/)のメンテナであるJosh氏が「BiomeのようなRustベースのLinter/Formatterツールについてどう思うか？いつか`ESLint`や`typescript-eslint`の役割を引き継ぐと思うか？」などの質問に対して多角的な観点から回答を与えている一連のXポストです。

## Making Sense of React Server Components

https://www.joshwcomeau.com/react/server-components/

React Server Componentsの解説記事です。SSRやSSGとの違いなどの基礎的な部分から図やグラフ等を用いて詳しく説明しており、React Server Componentsの入門記事として有用です。

## Using Zig in our incremental Turborepo migration from Go to Rust

https://vercel.com/blog/how-we-continued-porting-turborepo-to-rust

Vercel社が手がけるビルドシステム[Turborepo](https://turbo.build/repo)のコードベースをGoからRustへ移行にするにあたって、[Zig](https://ziglang.org/)を使用していることを紹介しています。

## Static Hermes (React Native EU 2023 Announcement)

https://speakerdeck.com/tmikov2023/static-hermes-react-native-eu-2023-announcement

React Nativeで動作しているMeta製のJavaScriptランタイム[Hermes](https://github.com/facebook/hermes)の次世代バージョンStatic Hermesの紹介スライドです。Static Hermesでは、TypeScriptやFlowの型情報を用いてパフォーマンスの最適化をしているのが特徴です。

## Bun 1.0

https://bun.sh/blog/bun-v1.0

9/8に、JavaScriptランタイムBun 1.0がリリースされました。Bunは、Node.jsとの互換性を持ちつつ、Node.jsよりも高速に動作することが特徴です。

## CSS View Transitions Module Level 1 publication history

https://www.w3.org/standards/history/css-view-transitions-1/

View Transitions APIが"Working Draft"から"Candidate Recommendation Snapshot"に移行しました。現在、View Transitions APIはChromeなどの一部ブラウザしか対応していませんが、今回のステータス変更により他のブラウザでも実装が進むことを期待できます。

[Astro 3.0](https://astro.build/)を用いながらView Transitions APIを駆使したサイトが有志の手で作られており、当APIの利用例として参考になります。

https://spotify-astro-transitions.vercel.app/

## Deno KV is in Open Beta

https://deno.com/blog/kv-open-beta

[Deno KV](https://deno.com/kv)がOpen Beta版になり、誰でも利用することができました。OAuthが簡単にできる機能をはじめとするいくつかの機能追加も伴っています。

## I am happy to see formatting rules being deprecated in the core if they can help save the maintenance efforts, as I stated in eslint/eslint.org#435 (comment).

https://github.com/eslint/eslint/issues/17522#issuecomment-1714223648

ESLintのフォーマット/スタイリングに関するルールを移管する提案です。現在、ESLintのフォーマット/スタイリングに関するルールはESLintのコアに存在しており、主にESLintチームがメンテナンスしています。ESLint上でこれらのルールをDeprecatedにした上で、これらのルールのメンテナンスをコミュニティに移管しようとする動きが存在します。

上記の投稿の後、`eslint-stylistic`という新たなorganizationが作成されました。

https://github.com/eslint-stylistic

## Four common types of code coverage

https://web.dev/ta-code-coverage/

コードカバレッジに関する解説記事です。コードカバレッジの主要な4つのタイプ、テストの種類（Unit/Integration/E2E）に応じたコードカバレッジの扱い方、コードカバレッジを扱う上での注意点などが解説されています。

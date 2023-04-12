---
title: "Chrome 113 でWebGPUをデフォルト利用可能になど : Cybozu Frontend Weekly (2023-04-11号)" # 目立ったニュースを選ぶ
emoji: "🌊" # お好きな絵文字を
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["CybozuFrontendWeekly", "frontend"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは! サイボウズ株式会社フロントエンドエンジニアの [おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com) です。

# はじめに

サイボウズでは毎週火曜日に Frontend Weekly という「一週間にあったフロントエンドニュースを共有する会」を社内で開催しています。

今回は、2023/04/11 の Frontend Weekly で取り上げた記事や話題を紹介します。

# 取り上げた記事・話題

## Powering a serverless Web: Vercel joins AWS Marketplace – Vercel

https://vercel.com/blog/vercel-joins-aws-marketplace

4/5 に Vercel が [AWS Marketplace](https://aws.amazon.com/marketplace/pp/prodview-lwqascgzju3bo) で利用できるようになりました。

これにより、AWS アカウントを通じて Vercel を導入することが可能になりました。

## New http://nextjs.org just dropped

https://twitter.com/rauchg/status/1643977860024254466

4/6 に Next.js のサイトが新しくなりました。

https://nextjs.org/

新しいサイトでは、[Masonry レイアウト](https://developer.mozilla.org/ja/docs/Web/CSS/CSS_Grid_Layout/Masonry_Layout)が導入されるなどの変更が加えられております。

## The future of Chakra UI

https://www.adebayosegun.com/blog/the-future-of-chakra-ui

3/27 に投稿された本記事では、[Chakra UI](https://chakra-ui.com/)の今後の開発計画について取り上げられています。

- ゼロランタイム CSS-in-JS の導入
- State Machine を用いたコンポーネントのモデル化
- Headless Component System への移行

などの計画が述べられていました。

## Chrome ships WebGPU - Chrome Developers

https://developer.chrome.com/blog/webgpu-release/

[5/2 に安定版のリリースが予定されている](https://chromiumdash.appspot.com/schedule) Chrome 113 で WebGPU がデフォルトで使えるようになります。

WebGPU は、WebGL よりも柔軟かつ高度な GPU プログラミングを可能にする API 仕様です。

機械学習ライブラリの[TensorFlow.js](https://github.com/tensorflow/tfjs)や、3DCG ライブラリの[Three.js](https://threejs.org/)などで WebGPU 対応が進められています。

## フロントエンドテスト、モジュールモックで Storybook のインタラクションテストの開発コストを下げる

https://zenn.dev/sora_kumo/articles/43f399cc73c0f3

Storybook 上でのモジュールのモックを可能にするライブラリ[storybook-addon-module-mock](https://github.com/ReactLibraries/storybook-addon-module-mock)の紹介記事です。

Storybook は、ブラウザで動作を確認しながらテストコードを確認できるメリットを持ちますが、一方でモジュールのモック機能を持たないため、Jest でいう`jest.mock`のような機能を実現するために独自の実装が必要でした。このライブラリはそうした課題の解決にアプローチしてくれます。

この記事は、具体的な実装例を通じてライブラリの利用方法をわかりやすく解説しています。

## Next.js 13.3

https://nextjs.org/blog/next-13-3

4/7 に[Next.js 13.3](https://github.com/vercel/next.js/releases/tag/v13.3.0)がリリースされました。

本バージョンでは、`<head>`タグの中に記す情報を扱う Metadata API の拡充や、App Router における静的エキスポートの対応などの数多くの機能追加が行われています。

## unjs/magicast

https://github.com/unjs/magicast

4/5 に[Anthony Fu](https://antfu.me/)さんが、ライブラリ Magicast をリリースしました。

読みやすいプログラムによって JavaScript や TypeScript のソースコードに変更を加えることを可能にします。

## CSS Creator Håkon Wium Lie Interview by Evrone

https://evrone.com/hakon-wium-lie-interview

CSS の生みの親の一人として知られる[Håkon Wium Lie](https://twitter.com/wiumlie)さんのインタービュー記事です。

CSS を提案するまでの彼の人生や、HTML と CSS を手書きで直接実装することがほとんどなくなった現状に対する私見など、様々な話題について触れられています。

## ⚛️ Dan Abramov explores React Server Components with us! [VOD]

https://youtu.be/Fctw7WjmxpU

Redux などの開発で知られる開発者[Dan Abramov](https://twitter.com/dan_abramov)さんが、React Server Components について説明している動画です。動画は 3 時間 55 分あります。

図やコードを交えながら説明しているため、決して英語が得意でなくともおおよその内容を把握できるようになっています。

## Largest Contentful Paint change in Chrome 112 to ignore low-entropy images

https://chromium.googlesource.com/chromium/src/+/refs/heads/main/docs/speed/metrics_changelog/2023_04_lcp.md

4/6 リリースの Chrome112 から、LCP の計測において画像 px 数に対して情報量の少ない画像を無視するようになりました。具体的には「**画像のデータ量 / px 数 < 0.05 bits**」の画像が対象です。

今までこうした画像が極めて早い段階で描画されていたために LCP が短く評価されていたようなサイトは、LCP が増大する可能性があります。

## WebAssembly tail calls · V8

https://v8.dev/blog/wasm-tail-call

末尾呼出し最適化（Tail Call Optimization）は、関数の呼び出し階層が深くなりすぎた時に呼び出し情報のスタックがオーバーフローすることを防ぐために行われる最適化処理の一つです。

この記事では、V8 における末尾呼出し最適化の技術的工夫について扱っています。

# あとがき

サイボウズでは毎月、最終火曜日の 17 時から Frontend Monthly というイベントを YouTube Live で開催しています。その月のフロントエンド注目ニュースや、ゲストを呼んでの対談など、フロントエンドに関する発信をしていますので是非どうぞ！

https://cybozu.github.io/frontend-monthly/

また、サイボウズでは一緒にサイボウズのフロントエンドをより良くする仲間を募集しています。興味ある方はこちら ↓ から！

**【フロントエンドエキスパート】**
サイボウズのフロントエンドを最高にするためのチームです。

https://cybozu.github.io/frontend-expert/

https://cybozu.co.jp/recruit/entry/career/front-end-expert.html

**【フロントエンドエンジニア（kintone アーキテクチャ刷新 PJ）】**
クラウドサービス「kintone」のフロントエンドを新しくしています。

https://blog.cybozu.io/archive/category/%E3%83%95%E3%83%AD%E3%83%AA%E3%82%A2

https://cybozu.co.jp/recruit/entry/career/front-end-engineer-kintone.html

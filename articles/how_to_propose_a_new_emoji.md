---
title: "誰でも簡単⁉️👀 絵文字ができるまで😃👍"
emoji: "🗿"
type: "tech"
topics: ["絵文字", "unicode", "design"]
published: false
publication_name: "cybozu_frontend"
---

こんにちは！サイボウズ株式会社フロントエンドエンジニアの [おぐえもん（@oguemon_com）](https://twitter.com/oguemon_com) です。

先日開催された社内イベント[Cybozu Frontend Day 2023](https://blog.cybozu.io/entry/2023/07/31/170000)にて私が発表した[絵文字の仕様策定](https://speakerdeck.com/oguemon/how-to-propose-a-new-emoji)に関する紹介を、当時の時間的制約から泣く泣く割愛した内容を加えた上で文章の形にまとめました。

@[speakerdeck](37b83d44e33c4925acd3215d2a292c23)

また、情報は全て**2023年8月1日現在**のものです。

# はじめに

今や「ぴえん🥺」や「おじさん構文」などの様々な形で老若男女を問わず私たちの生活・文化に深く根ざしている絵文字。ところで、そんな絵文字たちにも**生みの親**がいることを意識したことがありますか？

例えばこちらの絵文字にも生みの親がいます。

![yawning face](/images/how_to_propose_a_new_emoji/yawning_face.webp)

🥱は、[Jay Peters](https://twitter.com/jaypeters)さんが2017年9月に提案しました。

https://www.theverge.com/21327599/how-to-make-emoji-yawning-face-waffle-proposal-unicode

Jay Petersさんの職業は**ニュース編集者**。決してデザイン事務所やGAFAなどのエンジニア・デザイナーではありません。

このように、**誰でも新しい絵文字を提案することができます**。

この記事では、そういえば広く知られていない絵文字にまつわる色々をご紹介します。

- 絵文字ができるまでの流れ
- 絵文字の提案方法
- 提案の通過率

# 絵文字（Emoji）とは

絵文字とは、文字通り絵で表現された文字のことで、😀🥺💦💕🏠💻🌊👿🐱💢などがその例です。海外では**Emoji**と呼ばれており、日本語が由来の万国共通語になっています。

ちなみに、似た概念の顔文字（＼(^o^)／など）は**Emoticon**と呼ばれていて両者は区別されています。

文字コードにおける絵文字の歴史は古く、日本では1959年に野球ボールの絵文字（⚾️）が協定新聞社用の文字コード（CO-59）に登場します。その後、1999年にNTTドコモのフィーチャーフォン（ガラケー）に絵文字が登場し、ケータイ文化を中心に絵文字が広がっていきます。

https://www.moma.org/collection/works/196070

そして、2010年には業界標準規格のUnicode 6.0に**Emoji**が追加され、端末間の互換性が大幅に向上するとともに世界中で絵文字が使用されるようになりました。

PC・スマホで使われる絵文字は、今やUnicodeの規格で定められている**Emoji**がデファクトスタンダードです。ですので、以降ではUnicodeの**Emoji**について扱います。

# Emojiの仕様策定機関

EmojiをはじめとするUnicodeの仕様は[Unicodeコンソーシアム](https://home.unicode.org/)が策定しています。

Unicodeコンソーシアムは数多くの会員で構成されていますが、仕様策定への議決権を持つのは、年5万ドルの会費の**Full Members**（1票）と、年2万ドルの会費の**Supporting Members**（0.5票）の2種類の会員です。

Full Membersは、Adobe社やairbnb社、NETFLIX社、GAFAなどの大企業10社で構成されています。そして、Supporting Membersは、バングラデシュ政府やオマーン政府などの3団体で構成されています。

https://home.unicode.org/membership/members/

Unicodeの仕様策定のなかでもEmojiの仕様の候補案は**Emoji分科会**（Emoji Subcommittee）が策定します。Emoji分科会の座長はGoogle社のデザイナーである[Jennifer Daniel](https://twitter.com/jenniferdaniel)さんで、彼女もまた過去に数多くの絵文字を生み出しています（🥹🫠🫥🥲🫡など…）。

# Emojiができるまでの流れ（🫚を例に）

新しいEmojiの作成は、誰かが新しいEmojiの提案書（Proposal）をEmoji分科会に提出するところから始まり、世界中のデバイスで使えるようになるところがゴールです。

ここでは、UnicodeのEmoji仕様の最新版である[Emoji 15.0](https://www.unicode.org/reports/tr51/tr51-23.html)で追加された今一番新しいEmojiの1つ、**生姜の根**（🫚）を例にして、Emojiができるまでの流れを追っていきます。

![ginger root](/images/how_to_propose_a_new_emoji/ginger_root.webp)

もし手元のデバイスで「🫚」←ここに生姜が表示されていない方は、OSのバージョンが古い可能性があるのでアップデートしましょう。iPhoneならばiOS16.4から使用可能です。

## 1. 提案書の提出

生姜のEmojiの必要性を感じたJohannes Erbさん、Pascal Fiedlerさん、Paulina Schumannさんの3名が**2021年5月5日**に連名で提案書（Proposal for Emoji: GINGER）を提出しました。

![ginger proposal](/images/how_to_propose_a_new_emoji/ginger_proposal.webp)
_[提出された提案書](https://www.unicode.org/L2/L2021/21200-ginger-emoji.pdf)の一部_

採択された絵文字の提案書は基本的にUnicodeコンソーシアムのドキュメントとして公開されています^[[Emoji Proposals, v15.0](https://www.unicode.org/emoji/charts/emoji-proposals.html)]。この提案書も例外でなく、以下のリンクから確認できます。

https://www.unicode.org/L2/L2021/21200-ginger-emoji.pdf

## 2. Unicodeコンソーシアムによる仕様策定

提案書がEmoji分科会による審査を通過すると、仕様化に向けた議論や調整がはじまります。以下はその一部です。

### Emoji案の登場

2021年10月4日、Unicodeの技術会議である[UTC169](https://www.unicode.org/L2/L2021/21167.htm)にあわせて、Emoji分科会の[2021年Q4レポート](https://www.unicode.org/L2/L2021/21172r-esc-recs.pdf)が公開され、当時の次期仕様であるEmoji 15.0における追加Emoji候補案が登場しました。

### 文字コード案の付与

2021年11月15日時点の[Emoji Candidates (Provisional)](https://www.unicode.org/review/pri435/pri435-background-emoji-candidates.pdf)には、Emojiの候補に文字コードなどの案が加えられています。この候補案は、[PRI #435](https://www.unicode.org/review/pri435/)^[PRI = Public Review Issues]として2022年4月10日までフィードバックを受け付けていました。

### 名称の修正

2022年1月25日、Unicodeの技術会議[UTC170](https://www.unicode.org/L2/L2022/22015.htm)にて、Emoji分科会の[2021年Q4レポート](https://www.unicode.org/L2/L2022/22021-esc-report-q1.pdf)が公開。いくつかのEmoji候補案に対して名称の変更などの修正を推奨する旨が記載されていました。

ここで、🫚は**Ginger**（生姜）から**Ginger Root**（生姜の根）に改められました。これは、`ginger`には「赤毛の人」「赤毛の〜」といった意味があり、混同のおそれがあるとの指摘が寄せられたからです^[[Accumulated Feedback on PRI #435](https://www.unicode.org/review/pri435/feedback.html)]。

### Unicode 15.0仕様書の作成とパブリックレビュー

Emoji 15.0などを含めたUnicode全体の新仕様であるUnicode 15.0の仕様書が作成され、パブリックレビューが行われました。

2022年2月から7月にかけて行われました。公開レビューには2段階あり、2〜4月に[アルファレビュー](http://blog.unicode.org/2022/02/unicode-150-alpha-review.html)が、6〜7月に[ベータレビュー](http://blog.unicode.org/2022/05/unicode-150-beta-review.html)が行われました。ベータレビュー用の開始時点で、文字の名称などが確定します。

### Unicode 15.0仕様書のリリース

2度のパブリックレビューを経て仕上がったUnicode 15.0の仕様書は、**2022年9月13日**にリリースされました！これで新しい仕様を使えるようになりました。

https://twitter.com/unicode/status/1569800516628283392?s=20

Unicode 15.0のリリースを知らせる記事には、🫚をはじめとする新しいEmojiの追加についても触れています。

http://blog.unicode.org/2022/09/announcing-unicode-standard-version-150.html

## 3. 各ベンダーによるEmojiの実装とリリース

UnicodeコンソーシアムがUnicodeの仕様を定めても、Apple社やGoogle社などのベンダーが自身のソフトウェア製品・サービス（iOS、Android、Facebookなど）に仕様通りの実装を追加しなければ世界中の人たちは新しいEmojiを使うことができません。

Unicode 15.0のリリースを受けて、ベンダー各社はEmojiの実装と公開を正式に進めていきます。

例えばApple社の場合、2023年2月16日に**iOS16.4のベータ版**をリリースして、開発者向けに新しいEmojiを公開。そして、2023年3月27日に**iOS16.4の正式版**をリリースして、ついにiPhoneユーザーが🫚を使えるようになりました！

https://support.apple.com/ja-jp/HT213407#164

他にもGoogle社やMeta社（Facebook）、X社（X / Twitter）などもそれぞれのデザインの🫚を実装してリリースしました。

https://emojipedia.org/ginger/

この時点で、🫚は**提案書の提出から2年近く経過**しています。このように、Emojiができるまでには長い年月がかかります。

# Emojiの提案方法

Emojiの提案は、次の2ステップで誰でも簡単に行うことができます。

1. 所定のフォーマットのPDFで提案書を作成
1. 提案書をUnicodeコンソーシアムのEmoji分科会に送付

今は新しいEmojiの提案書を受け付けていませんが、2024年4月から受け付けを再開する予定です。

これから述べる採択条件の話を含め、Emojiの提案については次のガイドラインにまとめられています。

https://unicode.org/emoji/proposals.html

# Emojiの採択の条件

Emojiの採択にはたくさんの条件があります。

条件はOKな条件（[Selection Factors for Inclusion](https://www.unicode.org/emoji/proposals.html#selection_factors_inclusion)）とNGな条件（[Selection Factors for Exclusion](https://www.unicode.org/emoji/proposals.html#selection_factors_exclusion)）に二分されます。ここではそれぞれの条件の一部を紹介します。

## OKな条件

あることが望ましい条件です。決してどれか1つでも不満足ならアウトというわけでなく、総合的に評価されます。

### Usage level

簡単に言うと、多くの利用が見込めるかどうかです。提案書では主に次の4つの観点でエビデンスを示せます。

#### 1. Frequency

高頻度で使われるかどうかです。ガイドラインでは、次のサービスを用いた調査結果を示すことを必須としています。

| サービス                    | 備考                                         |
| :-------------------------- | :------------------------------------------- |
| Google Search               | **7.5億件**が目安                            |
| Bing Search                 | **2,500万件**が目安                          |
| Google Video Search         | **7,500万件**が目安                          |
| Google Trends: Web Search   | *elephant*との比較結果を示す必要があります🐘 |
| Google Trends: Image Search | *elephant*との比較結果を示す必要があります🐘 |

#### 2. Multiple usages

1つのEmojiで複数の使い方ができるか、Emojiが顕著な比喩的に参照されたり、何かの象徴性を持っているかどうかです。

例えば、🔥は「火」だけでなく「進行中」や「熱意」などの表現にも使えます。

#### 3. Use in sequences

他のEmojiと組み合わせて使うことができるかどうかです。

例えば、💦🧼🤲で「手洗い」を表現できますし、🗑🔥で「燃えるゴミ」を表すことができます。

#### 4. Breaking new ground

要は、Emojiの新境地を切り開く新規性があるかどうかです。

例えば、掃除を示す🧹のEmojiがある現状において「掃除機」のEmojiを提案することは新境地の開拓とは程遠いです。

既存のEmojiで表現できない概念を象徴できるものが望まれます。

### Distinctiveness

Emojiが明確に識別できるものであることが望まれます。

- それを認識するのに特別な知識が必要でないこと
- たとえ携帯電話の画面に映る小さなアイコンであっても識別できること

などがポイントです。

### Compatibility

既存サービスの絵文字に対する互換性のために提案されたものかどうかです。

例えば、🤔（考える顔）はGmailの絵文字*THINKING*から移植されました^[[Emoji Additions](https://www.unicode.org/L2/L2014/14174r-emoji-additions.pdf)]。

### Completeness

一揃いの絵文字たちで欠けているものを補っているかどうかです。

例えば、🦂（サソリ）は12星座の中でEmojiから欠けていたので提案されました^[[Emoji Additions](https://www.unicode.org/L2/L2014/14174r-emoji-additions.pdf)]。

## NGな条件

あるとダメな条件です。必ずしも一発アウトではないものの、これらの条件を満たすと採択されにくくなります。

### Petitions or “frequent requests”

それが請願だったり、頻繁にリクエストされるものであってもダメです。「みんなが求めている」という主張は十分な信頼性がなく、提案の根拠として弱いわけです。

🌭（ホットドック）や 🌮（タコス）は、署名キャンペーン^[[I humbly request that you add a hotdog symbol to the emoji set, and furthermore ketchup shall not be used in the making of this hot dog emoji.](https://www.change.org/p/president-of-the-united-states-i-humbly-request-that-you-add-a-hotdog-symbol-to-the-emoji-set-and-furthermore-ketchup-shall-not-be-used-in-the-making-of-this-hot-dog-emoji)]^[[Create a taco emoji.](https://www.change.org/p/apple-inc-create-a-taco-emoji-5d919496-a3e5-4988-a53e-06daae44f9da)]がキッカケで提案されましたが、これは請願されたから採択されたのでなく、提案書の客観的根拠が認められて採択されました。

### Overly specific

示しているものが細かすぎるものです。

例えば、🏨（ホテル）が存在する中での🏩（ラブホテル）、🐪（ラクダ）が存在する中での🐫（フタコブラクダ）は詳細すぎますよね。

### Already representable

既にある絵文字で意味を表現できる絵文字です。例えば、手洗いをしている絵文字の案は、前にも出てきた💦🧼🤲で「手洗い」を表現できるのでこの項目に該当します。

### Logos, brands, other third-party IP rights, UI icons, signage, specific people, specific buildings and landmarks, deities

日本語にすると次の通りです。

- ロゴ
- ブランド
- その他の第三者の知的財産権
- UIアイコン
- 標識
- 特定の人
- 特定の建物やランドマーク
- 神々

この基準に照らし合わせると、例えば次のようなEmojiはNGです。

- ⏯️ （再生・停止ボタン）や ⏪️（早戻しボタン） → **UIアイコン**
- ⛔（立入禁止）や 🚸（通学路） → **標識**
- 🗼（東京タワー）や 🗻（富士山）、 🗿（モアイ像） → **特定の建物やランドマーク**

### Transient

一過性のものや、流行りのものは、たとえ現在使われていても将来も使われる見込みが少ないので採択されにくいです。

例えば、📟（ポケベル）や📼（ビデオカセット）は、かつて多用されていたアイテムですが、今やほとんど使われていません…

### Region flags without code

Unicodeの地域コードを持たない地域の旗は採択されません。

国旗をはじめとする地域の旗のEmojiは、その国家・地域がUnicode region codesに登録されたときに自動的に追加されるようになっています。

### Variations on direction

既存のEmojiに対して方向が違うだけのものです。

👉に対する👈👆👇、🤜に対する🤛などがそれです。

とはいえ、2023年リリース予定のEmoji 15.1では、複数の方向を持つEmojiのセットを追加する予定があり、Emoji分科会はEmojiの向きの違いが生み出す表現の可能性に注目し始めているようです。

http://blog.unicode.org/2023/01/whats-new-in-emoji-151.html

### Includes text

テキストが含まれているものです。その文字の言語利用者以外に通じにくいからです。

例えば、🈯️ 🈴 🈺 🈁 🈳のようなものです。

## Emojiの提案の通過率

Emoji分科会は、過去にリクエストされたEmojiと、その審査結果を公開しています。

https://unicode.org/emoji/emoji-requests.html

ここには**1231件**のリクエストが掲載されていますが、そのステータスの内訳は次の通りです。

| ステータス                   | 件数 |  割合 | 備考                      |
| :--------------------------- | ---: | ----: | :------------------------ |
| Declined                     |  803 | 65.2% | 拒否                      |
| Declined, Duplicate Proposal |   58 |  4.7% | 拒否（重複）              |
| Under Consideration          |    7 |  0.6% | 検討中                    |
| Expired                      |  109 |  8.9% | 期限切れ                  |
| Prioritization Pending       |   41 |  3.3% | 優先順位の関係で保留中    |
| Released as Emoji            |  213 | 17.3% | Emojiとしてリリース済み🎉 |

このように、採択されたEmojiの数は、**提案されたEmojiの約17%に過ぎません**。なかなかの狭き門であることが判ります。

例えば、DeclinedされたEmojiの案の中には次のようなものがあります。

- 3D printer
- bamboo^[竹が拒否された一方で、🎋(Tanabata Tree)というEmojiがあります。]
- Electric Bass
- Hairbrush
- Head louse（アタマジラミ）
- Jam
- Koi（錦鯉）
- Prison
- Programming
- SAUSAGE
- VR Headset

過去2年間にDeclineされたEmojiは再審査の対象になりません。もし新しいEmojiの提案をするなら、過去の提案内容を確認して、同じようなものがないか確認しましょう。

# まとめ

私たちが使用している絵文字の代表格であるUnicodeのEmojiは提案者に制約がないので、「このEmojiはワシが作った👴」と言えるチャンスが誰にでもあります。

しかし、Emojiの採択にはさまざまな条件があり、提案されたEmojiのうち採択されるのはごく一部（2割以下）です。さらに採択されるまでには2年前後の長い年月がかかるので、「このEmojiはワシが作った👴」と言うには険しい道のりを歩む必要があります。

ちなみに、「NGな条件」のところで、既存のEmojiを例としてたくさん列挙しました。今の条件では高確率で拒否されるこれらがなぜEmojiとして存在しているのか。それは、Emojiの仕様が最初に策定されたとき、絵文字の機器間の互換性を重視して、日本の携帯電話をはじめ当時あった絵文字をそのまま採用したからです。

こうした背景から、現在に至るまでEmojiの種類や絵柄には日本の文化や言葉に根ざしたものが数多く存在しています。

🎌🗾👹👺🙈🙉🙊👾💮🍢🍲🍣🍥🍡🍵🍶📛🔰🗻🗼🌊🎋🎍🎎🎏🎐🎑🎴🏮🧮🚄🚅🈁🉐🈯️🈲🈺🈁🈳…

このように、日本がEmojiに対して持っている先行者利益のようなものを享受して、日本ならではなEmojiをたくさん使っていくのも面白いかもしれませんね。

# おまけ

🗿（モアイ）の絵文字は、2016年にリリースされたEmoji 3.0まで、イースター島のモアイ像（Moai）のEmojiでなく、日本の**モヤイ像**（Moyai）のEmojiだったのをご存知でしょうか？

モヤイ像は、モアイ像をモデルにした伊豆諸島名物の石像のことで、渋谷駅前に佇んでいるものが有名です。

![渋谷駅前のモヤイ像](/images/how_to_propose_a_new_emoji/moyai_sibuya.webp)
_渋谷駅前のモヤイ像_

2009年に提出された提案書には、「**MOYAI \* Japanese stone statue like Moai on Easter Island**」と明記されています。

![MOYAIの提案書](/images/how_to_propose_a_new_emoji/moyai_proposal.webp)
_[Emoji Symbols Proposed for New Encoding](https://www.unicode.org/L2/L2009/09026r-emoji-proposed.pdf)より_

モヤイ像のEmojiは、auの携帯電話で利用できた**EZweb絵文字**に収録されたのがはじまりで、その後、他種端末への互換性のためUnicodeのEmojiに採用され、全世界で利用できるようになりました。その後、Emoji 4.0からは**Moai**という名称に変更されています。

![EZweb絵文字](/images/how_to_propose_a_new_emoji/moyai_kddi.webp)
_[EZweb絵文字一覧【タイプＤ】](https://www.au.com/ezfactory/tec/spec/pdf/typeD.pdf)より_

日本の絵文字がEmojiに与えていた影響の大きさを伺い知ることができる興味深い事例です。

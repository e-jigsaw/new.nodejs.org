---
title: Weekly Update - Feb 13th, 2015
author: Tierney Coren (@bnb)
date: 2015-02-13T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-02-13
layout: blog-post.hbs
---

<!--
## io.js support added by...
-->

## io.jsサポートの追加
* [Postmark](http://blog.postmarkapp.com/post/110829734198/its-official-were-getting-cozy-with-node-js)
* [node-serialport](https://github.com/voodootikigod/node-serialport/issues/439)
* [Microsoft Azure](http://azure.microsoft.com/en-us/documentation/articles/web-sites-nodejs-iojs/)

<!--
## io.js breaks 10,000 stars on GitHub
-->

## Githubでio.jsが 10,000 Star を達成

<!--
On Feb. 13, io.js reached the goal of 10,000 stars on GitHub. We couldn't have done it without the support of the amazing community behind JavaScript. Thank you alll!
-->

2月13日、JavaScriptコミュニティの素晴らしいサポートのお陰で、io.jsに10,000のGithub Starがつきました。本当にありがとう！

<!--
## io.js 1.2.0 released
-->

## io.js 1.2.0 リリース

<!--
* **stream**: Simpler stream construction ([readable-stream/issues#102[(https://github.com/iojs/readable-stream/issues/102))
* **dns**: `lookup()` now supports an `'all'` boolean option, default to `false` but when turned on will cause the method to return an array of all resolved names for an address, see, ([iojs/pull#744](https://github.com/iojs/io.js/pull/744))
* **assert**: Remove `prototype` property comparison in `deepEqual()` ([iojs/issues#636](https://github.com/iojs/io.js/pull/636)); introduce a `deepStrictEqual()` method to mirror `deepEqual()` but performs strict equality checks on primitives ([iojs/issues#639](https://github.com/iojs/io.js/pull/639)).
* **tracing**: Add [LTTng](http://lttng.org/) (Linux Trace Toolkit Next Generation) when compiled with the `--with-lttng option`. Trace points match those available for DTrace and ETW. ([iojs/issues#702](https://github.com/iojs/io.js/pull/702))
* **docs**: Lots of doc updates, see individual commits; new Errors page discussing JavaScript errors, V8 specifics, and io.js specific error details.
* **npm** upgrade to 2.5.1
* **libuv** upgrade to 1.4.0, see libuv [ChangeLog](https://github.com/libuv/libuv/blob/v1.x/ChangeLog)
* Add new collaborators:
  * Aleksey Smolenchuk (@lxe)
  * Shigeki Ohtsu (@shigeki)
-->

* **stream**: よりシンプルなstream作成。 ([readable-stream/issues#102](https://github.com/iojs/readable-stream/issues/102))
* **dns**: `lookup()`メソッド で `'all'` オプションをサポート。この設定を有効にすると名前の解決が行われたすべてのアドレスを配列で返します(デフォルトは`false`に設定)。 ([iojs/pull#744](https://github.com/iojs/io.js/pull/744))
* **assert**: `deepEqual()`から`prototype`プロパティの比較を外しました。 ([iojs/issues#636](https://github.com/iojs/io.js/pull/636)) `deepEqual()`のミラーとして`deepStrictEqual()`メソッドを追加し、こちらがプリミティブの比較を行います。 ([iojs/issues#639](https://github.com/iojs/io.js/pull/639))
* **tracing**: `--with-lttng option` オプションを付けてコンパイルした場合に[LTTng](http://lttng.org/) (Linux Trace Toolkit Next Generation) が追加されます。 トレースポイントはDTraceとETWで使用可能なものと同じです。([iojs/issues#702](https://github.com/iojs/io.js/pull/702))
* **docs**: 多くのドキュメントがアップデートされました。新たに JavaScriptエラーについての[Errorsページ](https://iojs.org/api/errors.html)を追加、V8の詳細、io.jsに特化したエラーの詳細など（各コミットを参照してください）。
* **npm** を 2.5.1にアップグレード
* **libuv** を 1.4.0にアップグレード (詳しくはlibuvの[変更履歴](https://github.com/libuv/libuv/blob/v1.x/ChangeLog)へ)
* 新規コラボレーターの追加:
  * Aleksey Smolenchuk (@lxe)
  * Shigeki Ohtsu (@shigeki)

<!--
## Opened our doors to the international community
-->

## 世界中のコミュニティを受け入れ

<!--
View the [original article](https://medium.com/@mikeal/how-io-js-built-a-146-person-27-language-localization-effort-in-one-day-65e5b1c49a62) on Medium.
* Added interested contributors to teams for their language.
* Teams registered Twitter accounts for their teams and other relevant social media accounts.
* Teams came up with their own ways of working together, and they became more of "community organizers," as opposed to just "translators"
-->

Mediumに載せた[元記事](https://medium.com/@mikeal/how-io-js-built-a-146-person-27-language-localization-effort-in-one-day-65e5b1c49a62)を参照
* 参加したいと言ってくれたメンバーを各言語チームのコントリビューターとして追加
* 各チームごとにTwitterや地域に特化したソーシャルメディアアカウントを設置
* 各チームが独自にワークフローを設定することで「翻訳者」というよりも「コミュニティオーガナイザー」に

<!--
### Stats for Localizations:
-->

### ローカリゼーションの状況:

<!--
* 146 people signed up to help with the localizations the first day (over 160 signed up now)
* 27 languages communities created the first day (already up to 29)
-->

* 呼びかけ初日に146人がローカリゼーションチームに参加 (現在は160人以上)
* 初日だけで27言語のローカリゼーションチームが発足(現在は29言語)

<!--
### Language Communities
-->

### 各言語のコミュニティ

* [`iojs-bn`](https://github.com/iojs/iojs-bn) ベンガル語コミュニティ
* [`iojs-cn`](https://github.com/iojs/iojs-cn) 中国語コミュニティ
* [`iojs-cs`](https://github.com/iojs/iojs-cs) チェコ語コミュニティ
* [`iojs-da`](https://github.com/iojs/iojs-da) デンマーク語コミュニティ
* [`iojs-de`](https://github.com/iojs/iojs-de) ドイツ語コミュニティ
* [`iojs-el`](https://github.com/iojs/iojs-el) ギリシャ語コミュニティ
* [`iojs-es`](https://github.com/iojs/iojs-es) スペイン語コミュニティ
* [`iojs-fa`](https://github.com/iojs/iojs-fa) ペルシャ語コミュニティ
* [`iojs-fi`](https://github.com/iojs/iojs-fi) フィンランド語コミュニティ
* [`iojs-fr`](https://github.com/iojs/iojs-fr) フランス語コミュニティ
* [`iojs-he`](https://github.com/iojs/iojs-he) ヘブライ語コミュニティ
* [`iojs-hi`](https://github.com/iojs/iojs-hi) ヒンディー語コミュニティ
* [`iojs-hu`](https://github.com/iojs/iojs-hu) ハンガリー語コミュニティ
* [`iojs-id`](https://github.com/iojs/iojs-id) インドネシア語コミュニティ
* [`iojs-it`](https://github.com/iojs/iojs-it) イタリア語コミュニティ
* [`iojs-ja`](https://github.com/iojs/iojs-ja) 日本語コミュニティ
* [`iojs-ka`](https://github.com/iojs/iojs-ka) グルジア語コミュニティ
* [`iojs-kr`](https://github.com/iojs/iojs-kr) 韓国語コミュニティ
* [`iojs-mk`](https://github.com/iojs/iojs-mk) マケドニア語コミュニティ
* [`iojs-nl`](https://github.com/iojs/iojs-nl) オランダ語コミュニティ
* [`iojs-no`](https://github.com/iojs/iojs-no) ノルウェー語コミュニティ
* [`iojs-pl`](https://github.com/iojs/iojs-pl) ポーランド語コミュニティ
* [`iojs-pt`](https://github.com/iojs/iojs-pt) ポルトガル語コミュニティ
* [`iojs-ro`](https://github.com/iojs/iojs-ro) ルーマニア語コミュニティ
* [`iojs-ru`](https://github.com/iojs/iojs-ru) ロシア語コミュニティ
* [`iojs-sv`](https://github.com/iojs/iojs-sv) スウェーデン語コミュニティ
* [`iojs-tr`](https://github.com/iojs/iojs-tr) トルコ語コミュニティ
* [`iojs-tw`](https://github.com/iojs/iojs-tw) 台湾語コミュニティ
* [`iojs-uk`](https://github.com/iojs/iojs-uk) ウクライナ語コミュニティ


<!--
## io.js and Node.js
-->

## io.js と Node.js

<!--
View the [original article](https://medium.com/@iojs/io-js-and-a-node-js-foundation-4e14699fb7be) on Medium.
* Scott Hammond, CEO of Joyent, expressed his desire to bring io.js back to the node.js.
-->

[元記事を参照](http://blog.iojs.jp/io.js_and_node.js_Foundation.html)
* Joyent CEOのScott Hammond氏よりio.jsをnode.jsに戻したい意向を受けました

<!--
#### In only a few months io.js...
-->

### ここ数ヶ月でio.jsは...

<!--
* Has grown to 23 active core team members
* Has several working groups
* Has 29 language localization teams,
* Has drawn more contributors to the project than we’ve ever had in the history of node.js, and
* Has been able to release quality software at a good pace with the support of an exceptional community.
-->

* 23人のコアチームに成長
* いくつかのワーキンググループを結成
* 29言語へのローカリゼーションチームを発足
* node.js史上最多のプロジェクト参加者を惹きつけることに成功
* コミュニティのサポートを受けて、良いペースで質の高いソフトウェアのリリース

<!--
> We are eager to put this all behind us but we can’t sacrifice the progress we’ve made or the principles and open governance that got us here.
-->

> 分離についてはみんな早く水に流したいと思っていますが、これまでの進捗や、それを推し進めたオープンガバナンスの理念を捨てるわけにはいきません。

<!--
### The Future
-->

### 今後について

<!--
* Talks with the node.js foundation are ongoing.
* Once the foundation has a technical governance model you will see an issue on io.js’ GitHub about whether io.js should join.

  * This will be discussed and voted on openly in a public TC meeting following the governance rules we’ve already built.
-->

* node.js foundation との話し合いは現在も進行中です
* node.js Foundationがテクニカルガバナンスモデルを作り次第、io.jsのGithub issueにてio.jsがnode.jsに戻るべきかのディスカッションを行います
  * 私達の作ったガバナンスモデルにもとづいて、公開TCミーティングにてディスカッションとvoteを行います

<!--
> For the community, nothing has changed.
-->

> コミュニティの皆さんにとって現状は何も変わりません。

<!--
### What to do right now
-->

### 今できること

<!--
* Continue to send your pull requests to io.js
* Join one of the 27 [language localization teams](https://github.com/iojs/website/issues/125)
* Contribute to io.js’ working groups ([streams](https://github.com/iojs/readable-stream), [website](https://github.com/iojs/website), [evangelism](https://github.com/iojs/website/labels/evangelism), [tracing](https://github.com/iojs/tracing-wg), [build](https://github.com/iojs/build), [roadmap](https://github.com/iojs/roadmap)) and
* Continue to adopt io.js in your applications.
-->

* 今までどおりpull requestsをio.jsに送る
* [27言語のローカリゼーションチーム](https://github.com/iojs/website/issues/125)に参加する
* io.jsのワーキンググループに参加する([streams](https://github.com/iojs/readable-stream), [website](https://github.com/iojs/website), [evangelism](https://github.com/iojs/website/labels/evangelism), [tracing](https://github.com/iojs/tracing-wg), [build](https://github.com/iojs/build), [roadmap](https://github.com/iojs/roadmap))
* io.jsをあなたのアプリケーションで利用する

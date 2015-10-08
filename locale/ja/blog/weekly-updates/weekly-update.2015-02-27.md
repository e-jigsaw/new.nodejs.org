---
title: Weekly Update - Feb 27th, 2015
author: Emily Rose (@emilyrose)
date: 2015-02-27T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-02-27
layout: blog-post.hbs
---

<!--
# io.js 1.4.1 Release
-->

## io.js 1.4.1リリース

<!--
 _Note: version **1.4.0** was tagged and built but not released. A libuv bug was discovered in the process so the release was aborted. We have jumped to 1.4.1 to avoid confusion._
 -->

_注意: バージョン **1.4.0** はタグ付け・ビルドされましたがリリースはされていません（libuvにバグが発見されたためリリースを中止しました）。混乱を避けるため1.4.1へバージョンを上げています。_

<!--
 ## Notable changes
-->

### 主な変更点

* **process** / **promises**:  イベントループの中で、`Promise` が reject され、その `Promise` に対してのエラーハンドラが一つも存在しない時はいつでも `'unhandledRejection'` イベントが `process` オブジェクトに emit されるようになりました。イベントループが回った後で `Promise` が reject され、あるエラーハンドラがそれをキャッチした時に`'rejectionHandled'` イベントが emit されるようになりました。  [#758](https://github.com/iojs/io.js/pull/758) (Petka Antonov)
* **streams**: `tls.connect()` に対してのローレベルなソケットとして標準の Streams を使うことが出来るようになりました [#926](https://github.com/iojs/io.js/pull/926) (Fedor Indutny)
* **http**: `http.ClientRequest`がクライアントによって abort された時、新しい `'abort'` イベントが emit されます。 [#945](https://github.com/iojs/io.js/pull/945) (Evan Lucas)
* **V8**: V8 を4.1.0.21に アップグレードしました。 これには差止された修正が含まれます。差止された情報が開示されたときに詳細を得られるべきです。io.js が V8 4.2 にマージした時に、恐らくこの修正が含まれることになるでしょう、このアップグレード (v4.2) から ABI の互換性を壊す変更が発生することになります。 詳細は このディスカッションを見てください。 [#952](https://github.com/iojs/io.js/pull/952)
* **npm**: npm を 2.6.0 に アップグレードしました。新しいレジストリのサポートや`npm@3`への準備のための機能を含みます。詳細は[npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v260-2015-02-12)を見てください。 サマリ：
  * [#5068](https://github.com/npm/npm/issues/5068) 新しくログアウトコマンドを追加しました。 bearer-based と basic-based の両方で認証されたクライアントの上で便利になるでしょう。
  * [#6565](https://github.com/npm/npm/issues/6565) `peerDependency` の振る舞いが変更中であり、ドキュメントに注意を追加している事が警告されています。
  * [#7171](https://github.com/npm/npm/issues/7171) npm の次のメジャーバージョン (coming soon!) の中で `package.json` の `engineStrict` が削除される予定だと警告されています。
* **libuv**: libuvを1.4.2 にアップグレードしました。 詳細は [libuv ChangeLog](https://github.com/libuv/libuv/blob/v1.x/ChangeLog) を見てください。


<!--
# ARM offers support for io.js on ARMv8
-->

## ARMから、ARMv8でのio.jsサポートの意向

<!--
ARM contacted Rod Vagg, lead of the io.js Build Working Group, to offer their support to the io.js project. ARM and their hardware partners are on track to make ARMv8 a viable server platform and the nimble nature of server-side JavaScript make it a perfect fit to run on the new ARM.
-->

ARM からRod Vagg(Buildワーキング・グループリード)へio.jsをサポートしたい旨、連絡がありました。ARMと彼らのハードウェアパートナーはARMv8を実用的なサーバーとして仕上げる予定で、実行速度の早いサーバーサイドJavaScriptはARM上で動かすのに最適です。

<!--
 Since ARMv8 is already being adopted by mobile device manufacturers, newer versions of V8 already have good support. Because of V8's pivotal role in Android, io.js is perfectly suited to track that support, and even contribute to it given our new relationships with the V8 team.
 -->

ARMv8はすでにモバイル製造において採用されているため、新しいバージョンのV8サポートがあります。特にV8はAndroidにおいて重要な役割を果たしているため、io.jsがこの流れに沿うのは最適です。また最近のV8チームとのコラボレーションにより、io.jsからもARMに貢献できるでしょう。

<!--
 From the beginning of the io.js project, Rod has championed the role of ARM for io.js, for IoT, hobbyist, and server use. We already have ARMv6 builds of each release for devices such as Raspberry Pi. and ARMv7 builds for many more popular devices (including the Online Labs ARM-based cloud platform, who have also offered help to io.js). ARMv8 is the logical extension of this, but also has exciting potential for server-side applications, particularly given the new 64-bit support.
 -->

io.jsの開始当初から、Rodは IoT, ホビー用途, またサーバーとしてのARMの役割について大きな期待と支持をしてきました。すでに各リリースにおいてARMv6ビルド（Raspberry Piなど）とARMv7ビルド（多くの人気デバイス、例えばio.jsのサポートを表明しているOnline Labsのクラウドプラットフォームなど）を用意しています。ARMv8の追加は自然な流れですが、特に64-bitのサポートはサーバーサイドアプリケーションの可能性が広がります。

<!--
The build team is in the process of being given access to the Linaro ARMv8 Server Cluster for integration with the io.js CI platform, which should eventually lead to regular ARMv8 binary releases.
-->

Buildチームでは、io.jsのCIプラットフォームとの連携用にLinaro ARMv8 Server Clusterへのアクセスを得る予定で、これにより毎リリースでARMv8のバイナリ配布が可能になります。

<!--
## Community Updates
-->

## コミュニティの動き

<!--
* [**Reconciliation Proposal**](https://github.com/iojs/io.js/issues/978): The io.js project is preparing a plan for reconciliation that can be brought to The Node.js Foundation. Input from the community is very important at this early stage so please leave a comment.
* **New internal C++ Streams API**: A [fresh C++ Streams API](https://github.com/iojs/io.js/commit/b9686233fc0be679d7ba1262b611711629ee334e) landed in io.js this week, allowing you to wrap a TLS stream into another TLS stream.
* **io.js Roadmap**: [The Roadmap](https://github.com/iojs/io.js/blob/v1.x/ROADMAP.md) is the plan for the future of io.js. It presents the plans for the stability policy, and lists what the immediate priorities for io.js as a whole are.
* **Roadmap Slides Finished and Ready for Translation**: The set of introductory slides for the Roadmap of io.js [have been finished, and are ready for translation](https://github.com/iojs/roadmap/issues/18). Do you think you could present them to a group near you? Comment and we'll work with you to prepare you to present!
* **Microsoft io.js How-To for Azure Websites**: Microsoft [published a how-to](http://azure.microsoft.com/en-us/documentation/articles/web-sites-nodejs-iojs/) tutorial for their Azure platform that describes how to use io.js with Azure Websites.
* **Floobits moves to io.js**: The code pairing software Floobits [converted their platform to io.js](https://news.floobits.com/2015/02/23/on-moving-to-io.js/), in part because of frustration with Node's slower release cycle, because the inclusion of more ES6 features without the need for the `--harmony` flag, and because they felt changes from 0.10.0 to 0.12.0 weren't very big.
* **Anand Mani Sankar's _Node.js vs io.js: Why the fork?!?_**: Anand wrote a good, for the most part objective, [post about the recent history of io.js](http://anandmanisankar.com/posts/nodejs-iojs-why-the-fork/#.VO82hE60PVw.twitter), and what we hope to achieve with it. A good read for people who aren't engaged in the community to catch up with.
* **iojs-jp - New io.js Japanese Blog**: The iojs-jp community has created a [localized io.js related blog](http://blog.iojs.jp/) to disseminate content in their language. If you're interested, take a look!
* **iojs-cn - New io.js Chinese Blog**: Similarly to the iojs-jp community, the iojs-cn community created a [localized blog](http://cn.iojs.org/) to publish posts about io.js to in their language. Make sure to visit if you're curious about iojs-cn or Chinese news about io.js!
* **[Roadmap Slides Review](https://www.youtube.com/watch?v=etI_UD4wXlo)** - A review of the roadmap slides before they were released to ensure they met with the message the project upholds.
-->

* [**和解プロポーザル**](https://github.com/iojs/io.js/issues/978): io.js プロジェクトではNode.js Foundationとの話し合いに向けて和解プランを立て始めました。初期段階でのコミュニティ意見参加はとても重要です、ぜひコメントを。
* **新 C++ Streams 内部API**: 全く新しい [C++ Streams API](https://github.com/iojs/io.js/commit/b9686233fc0be679d7ba1262b611711629ee334e)が今週io.jsに追加され、TLS streamを他のTLS streamで包むことができるようになりました。
* **io.js ロードマップ**: 主に安定性ポリシーと直近の優先項目についての[将来プラン](https://github.com/iojs/io.js/blob/v1.x/ROADMAP.md)
* **ロードマップのスライド完成 (翻訳用に準備完了）**: io.jsのロードマップについての紹介スライドが[完成し翻訳用に準備完了](https://github.com/iojs/roadmap/issues/18)しました。ぜひローカルイベントで発表しませんか？ コメントしてくれたらプレゼン準備をお手伝いします!
* **MicrosoftによるAzure Websitesでのio.js解説**: Azure Websites上でのio.jsの[使い方ハウツー記事](http://azure.microsoft.com/en-us/documentation/articles/web-sites-nodejs-iojs/).
* **Floobitsがio.jsへ移行**: ペアプログラミングソフトのFloobitsがNodeの遅いリリースサイクル、io.jsで`--harmony`フラグ無しでのES6利用、また(node.jsの)0.10.0と0.12.0で大きな変更点がなかった事から[彼らのプラットフォームをio.jsへ移行](https://news.floobits.com/2015/02/23/on-moving-to-io.js/)
* **Anand Mani Sankarによる _Node.js vs io.js: Why the fork?!?_**: Anand による（ほぼ）客観的に書かれたio.jsの歴史とゴールついての[記事](http://anandmanisankar.com/posts/nodejs-iojs-why-the-fork/#.VO82hE60PVw.twitter)。 今までコミュニティ流れを追ってこなかった人にオススメ。
* **iojs-jp - io.js日本語ブログ**: 日本語コミュニティが[io.jsについての日本語ブログ](http://blog.iojs.jp/)を作成。興味がある場合はぜひチェックを!
* **iojs-cn - io.js中国語ブログ**: 日本語コミュニティと同じく、中国語コミュニティも[現地ブログ](http://cn.iojs.org/)でio.jsの情報発信を開始。中国語でのio.jsニュースに興味がある場合はぜひチェックを!
* **[ロードマップスライドのレビュー](https://www.youtube.com/watch?v=etI_UD4wXlo)** - スライドリリース前に行われたプロジェクトに沿ったメッセージになっているかの確認ミーティング

<!--
# io.js Support Added
-->

## io.jsサポートの追加

<!--
* **[Wallby.js](http://wallabyjs.com/)**, a while-you-write testing library for JavaScript, hit version 1.0 and [added support for io.js](http://dm.gl/2015/02/23/wallaby-version-one/)!
* **[jsdom](https://github.com/tmpvar/jsdom)**, an implementation of the WHATWG DOM and HTML standards, just hit [version 4.0.0](https://github.com/tmpvar/jsdom/blob/master/Changelog.md#400), which added a _requirement_ of io.js.
* **[give](https://github.com/mmalecki/give)**'s creator [tweeted](https://twitter.com/maciejmalecki/status/569629100215816192) that newer versions of give support io.js. Give is a git-based node.js/io.js version manager.
* The **Firebase Realtime Client**, the official web/node.js JavaScript client for Firebase, [tweeted](https://twitter.com/FirebaseRelease/status/570000737343647744) that they added support for io.js in [version 2.2.1](https://www.firebase.com/docs/web/changelog.html#section-realtime-client)
* **Semaphore**, a hosted continuous integrations service, [tweeted](https://twitter.com/semaphoreapp/status/570987355005431809) about added io.js support in their [Platform update on February 24th, 2015](https://semaphoreapp.com/blog/2015/02/17/platform-update-on-february-24th.html?utm_source=twitter&utm_medium=social&utm_content=platform_update_launch&utm_campaign=platformupdate).
-->

* **[Wallby.js](http://wallabyjs.com/)**　(javascrip用テストライブラリ)が バージョン1.0 で[io.jsをサポート](http://dm.gl/2015/02/23/wallaby-version-one/)!
* **[jsdom](https://github.com/tmpvar/jsdom)**　(DOMシュミレーションパッケージ) が[新バージョン 4.0.0](https://github.com/tmpvar/jsdom/blob/master/Changelog.md#400)でio.js_のみ_をサポート。
* **[give](https://github.com/mmalecki/give)**の作者が新バージョンのgiveではio.jsをサポートと[ツイート](https://twitter.com/maciejmalecki/status/569629100215816192) (giveはgitベースの node.js/io.js バージョンマネージャー)
* **Firebase Realtime Client** (Firebaseオフィシャルのweb/node.js JavaScript クライアント)の[ツイート](https://twitter.com/FirebaseRelease/status/570000737343647744)によるとio.jsのサポートを[バージョン 2.2.1](https://www.firebase.com/docs/web/changelog.html#section-realtime-client)で追加
* **Semaphore**（CIサービス）の[ツイート](https://twitter.com/semaphoreapp/status/570987355005431809)によると[2月24日のプラットフォームアップデート](https://semaphoreapp.com/blog/2015/02/17/platform-update-on-february-24th.html?utm_source=twitter&utm_medium=social&utm_content=platform_update_launch&utm_campaign=platformupdate)でio.jsのサポートを追加

---
title: Weekly Update - Mar 6th, 2015
author: Ross Kukulinski (@rosskukulinksi)
date: 2015-03-06T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-03-06
layout: blog-post.hbs
---

<!--
# io.js 1.5.0 Release
-->

## io.js 1.5.0 リリース

<!--
On Friday, March 6th, [@rvagg](https://github.com/rvagg) released io.js [**v1.5.0**](https://iojs.org/dist/latest/).  The complete change log can be found [on GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).
-->

3月6日に [@rvagg](https://github.com/rvagg) は io.js [**v1.5.0**](https://iojs.org/dist/latest/) をリリースしました。完全なチェンジログは [GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md) で確認できます。

<!--
### Notable changes
-->

### 主な変更点

<!--
* **buffer**: New `Buffer#indexOf()` method, modelled off [`Array#indexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf). Accepts a String, Buffer or a Number. Strings are interpreted as UTF8. (Trevor Norris) [#561](https://github.com/iojs/io.js/pull/561)
* **fs**: `options` object properties in `'fs'` methods no longer perform a `hasOwnProperty()` check, thereby allowing options objects to have prototype properties that apply. (Jonathan Ong) [#635](https://github.com/iojs/io.js/pull/635)
* **tls**: A likely TLS memory leak was reported by PayPal. Some of the recent changes in **stream_wrap** appear to be to blame. The initial fix is in [#1078](https://github.com/iojs/io.js/pull/1078), you can track the progress toward closing the leak at [#1075](https://github.com/iojs/io.js/issues/1075) (Fedor Indutny).
* **npm**: Upgrade npm to 2.7.0. See [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v270-2015-02-26) for details including why this is a semver-minor when it could have been semver-major.
* **TC**: Colin Ihrig (@cjihrig) resigned from the TC due to his desire to do more code and fewer meetings.
-->

* **buffer**: `Array#indexOf()` からモデル化した `Buffer#indexOf()` メソッドが追加されました。これは String と Buffer と Number を受け入れます。文字列は UTF8 として解釈されます。(Trevor Norris) [#561](https://github.com/iojs/io.js/pull/561)
* **fs**: `'fs'` のメソッドの `options` オブジェクトのプロパティは、`hasOwnProperty()` によるチェックすることはなくなりました。これにより、 `options` オブジェクトのプロトタイププロパティが適用されることを可能にしました。(Jonathan Ong) [#635](https://github.com/iojs/io.js/pull/635)
* **tls**: TLS のメモリリークのようなものが PayPal によって報告されました。最近変更された **stream_wrap** にこの原因が見られます。最初の修正は [#1078](https://github.com/iojs/io.js/pull/1078) ですが、[#1075](https://github.com/iojs/io.js/issues/1075) にて現在も修正中です。(Fedor Indutny)
* **npm**: npm のバージョンを 2.7.0 にアップグレードしました。semver-major にされている可能性が semver-minor である理由など、詳細については [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v270-2015-02-26) を参照してください。
* **TC**: Colin Ihrig (@cjihrig) がミーティングを減らし、よりコーディングに時間をあてるため TC を辞任しました。

<!--
### Known issues
-->

### 既知の問題

<!--
* Possible TLS-related memory leak, details at [#1075](https://github.com/iojs/io.js/issues/1075).
* Windows still reports some minor test failures and we are continuing to address all of these as a priority. See [#1005](https://github.com/iojs/io.js/issues/1005).
* Surrogate pair in REPL can freeze terminal [#690](https://github.com/iojs/io.js/issues/690)
* Not possible to build io.js as a static library [#686](https://github.com/iojs/io.js/issues/686)
* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/iojs/io.js/issues/760) and fix in [#774](https://github.com/iojs/io.js/issues/774)
-->

* TLS に関連するメモリリークがあります。詳細は [#1075](https://github.com/iojs/io.js/issues/1075)。
* Windows はまだいくつかのマイナーなテストの失敗が報告されており、我々は優先的にこれら全ての対処を続けています。詳細は [#1005](https://github.com/iojs/io.js/issues/1005)。
* REPL 内のサロゲートペアがターミナルをフリーズさせることが可能です。[#690](https://github.com/iojs/io.js/issues/690)
* 静的ライブラリとして io.js をビルドすることができません。[#686](https://github.com/iojs/io.js/issues/686)
* child_process から生成された際の `process.send()` は[ドキュメントに記述されている](https://iojs.org/api/child_process.html#child_process_child_send_message_sendhandle)通り、本来は同期的に実行されるはずですが、1.0.2 によって発生した不具合により非同期的に呼び出されてしまうようになりました。詳細は [#760](https://github.com/iojs/io.js/issues/760) そして issue [#774](https://github.com/iojs/io.js/issues/774) で修正中です。

<!--
# Community Updates
-->

## コミュニティアップデート

<!--
* You can relax knowing that io.js and latest node.js [**are not affected**](https://strongloop.com/strongblog/are-node-and-io-js-affected-by-the-freak-attack-openssl-vulnerability/) by the [FREAK Attack](https://freakattack.com/).  You are running io.js or the latest version of node.js, right?
-->

* io.js と最新の node.js は [FREAK Attack脆弱性](https://freakattack.com/) の[**影響を受けません**](https://strongloop.com/strongblog/are-node-and-io-js-affected-by-the-freak-attack-openssl-vulnerability/) 。もちろん、 あなたはio.js か最新の node.js を使っていますよね？

<!--
* Walmart is now sponsoring a build machine for the io.js Jenkins CI system.  The @iojs/build team is working on creating io.js SunOS binaries (like you can get from nodejs.org).  A V8 fix ([iojs/io.js#1079](https://github.com/iojs/io.js/pull/1079)) needs to be landed first before more progress can be made.
* We would also like to thank the following companies for contributing hardware and related technology/support/engineering for io.js builds:
  * **Digital Ocean** (mainly Linux)
  * **Rackspace** (mainly Windows)
  * **Voxer** (OS X and FreeBSD)
  * **NodeSource** (ARMv6 & ARMv7)
  * **Linaro** (ARMv8)
  * **Walmart** (SmartOS / Solaris)
* The io.js community has been hard at work on the internationalization of all of its content.  There are now over 20 active languages published on [iojs.org](http://iojs.org) and i18n community sites.  Additionally, i18n links ([iojs/website#258](https://github.com/iojs/website/pull/258)) have been added to the website footer for easy access.  Are we missing your language?  [Help us add it!](https://github.com/iojs/website/blob/master/TRANSLATION.md)
* Speaking of translations, the [io.js roadmap presentation](http://roadmap.iojs.org/) has been updated to link to other language versions.
-->

* Walmart は io.js をビルドする Jenkins(CIシステム) のマシンを提供し始めました。@iojs/build チームは nodejs.org から取得することができるような  SunOS のバイナリの作成に取り組んでいます。より成果を出すためには V8 の修正([iojs/io.js#1079](https://github.com/iojs/io.js/pull/1079))が先に取り込まれる必要があります。
* 我々は io.js をビルドするためのハードウェア及び関連技術、サポート、エンジニアリングに貢献している以下の企業に感謝したいと思います:
  * **Digital Ocean** (mainly Linux)
  * **Rackspace** (mainly Windows)
  * **Voxer** (OS X and FreeBSD)
  * **NodeSource** (ARMv6 & ARMv7)
  * **Linaro** (ARMv8)
  * **Walmart** (SmartOS / Solaris)
* io.js コミュニティはそのコンテンツを全て国際化する仕事に励んできました。[iojs.org](http://iojs.org) と i18n のコミュニティサイトには20を超える言語が公開されています。更に、i18n のリンクは ([iojs/website#258](https://github.com/iojs/website/pull/258)) でウェブサイトの下部に簡単に追加することができます。あなたの言語が欠落していませんか？[追加の手助けをしてください！](https://github.com/iojs/website/blob/master/TRANSLATION.md)
* 翻訳といえば、[io.js ロードマッププレゼンテーション](http://roadmap.iojs.org/)も更新され、他の言語バージョンのリンクを追加しています。

<!--
* It seems that **PayPal** is running an experiment comparing [Kappa](https://www.npmjs.com/package/kappa)  on io.js vs node.js 0.12 vs node.js v0.10.  The PayPal team identified a likely TLS memory leak. Initial fix is in [#1078](https://github.com/iojs/io.js/pull/1078) and progress towards closing is in [#1075](https://github.com/iojs/io.js/issues/1075)
-->

* **PayPal** が実験的に [Kappa](https://www.npmjs.com/package/kappa) を io.js と node.js v0.12 と node.js v0.10 で比較をしたそうです。PayPal は TLS のメモリリークのようなものを特定しました。最初の修正は [#1078](https://github.com/iojs/io.js/pull/1078) ですが、[#1075](https://github.com/iojs/io.js/issues/1075) にて現在も修正中です。

<!--
* [**NodeSource**](http://nodesource.com) is now providing io.js [Linux binary](https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories) packages for Ubuntu/Debian as well as RHEL/Fedora distributions.
* The io.js [Docker build](https://registry.hub.docker.com/u/library/iojs/) is one of thirteen new [official Docker repositories](http://blog.docker.com/2015/03/thirteen-new-official-repositories-added-in-january-and-february/) added in January and February.
-->

* [**NodeSource**](http://nodesource.com) は io.js の [Linux binary](https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories) を Ubuntu/Debian や RHEL/Fedora のディストリビューションのパッケージとして提供を開始しました。
* 1月と2月に io.js の [Docker build](https://registry.hub.docker.com/u/library/iojs/) は13の新しい[公式 Docker リポジトリ](http://blog.docker.com/2015/03/thirteen-new-official-repositories-added-in-january-and-february/) に追加されました。

<!--
* NodeBots and IoT people should be happy to hear that the just-announced [**Tessel2**](http://blog.technical.io/post/112787427217/tessel-2-new-hardware-for-the-tessel-ecosystem) runs [io.js natively](http://blog.technical.io/post/112888410737/moving-faster-with-io-js).
* [**@maxbeatty**](https://twitter.com/maxbeatty) is working on a new version of the [jsperf.com](http://jsperf.com/) backend, running on io.js and it is entirely [open source](https://github.com/jsperf/jsperf.com).  Contributions are welcome!
-->

* NodeBots と IoT に関わる人々は [**Tessel2**](http://blog.technical.io/post/112787427217/tessel-2-new-hardware-for-the-tessel-ecosystem) が [io.js がネイティブになった](http://blog.technical.io/post/112888410737/moving-faster-with-io-js)ことを聞いて幸せでしょう。
* [**@maxbeatty**](https://twitter.com/maxbeatty) は新しいバージョンの [jsperf.com](http://jsperf.com/) のバックエンドを開発しています。jsperfのバックエンドは io.js 上で動作します。完全に[オープンソース](https://github.com/jsperf/jsperf.com)です。コントリビュート歓迎です！

<!--
* [@eranhammer](https://twitter.com/eranhammer) wrote a blog post called [The Node Version Dilemma](http://hueniverse.com/2015/03/02/the-node-version-dilemma/) which discusses the various node.js / io.js versions and proposes which ones to use and when to use them.
-->

* [@eranhammer](https://twitter.com/eranhammer) は [The Node Version Dilemma](http://hueniverse.com/2015/03/02/the-node-version-dilemma/) というブログ記事を書きました。これは様々な node.js と io.js のバージョンについて議論されており、これらを使うときにどれを使うべきかを提案しています。

<!--
# io.js Support Added
-->

## io.js のサポートが追加されたもの

<!--
* **[scrypt](https://npmjs.com/scrypt)** now supports io.js. Learn more from this [GitHub issue](https://github.com/barrysteyn/node-scrypt/issues/39)
* **[proxyquire](https://github.com/thlorenz/proxyquire)** v1.3.2 published with support for iojs.
-->

* **[scrypt](https://npmjs.com/scrypt)** は io.js のサポートをはじめました。詳しくは [GitHub issue](https://github.com/barrysteyn/node-scrypt/issues/39) にて。
* **[proxyquire](https://github.com/thlorenz/proxyquire)** は v1.3.2 で io.js のサポートを追加しました。

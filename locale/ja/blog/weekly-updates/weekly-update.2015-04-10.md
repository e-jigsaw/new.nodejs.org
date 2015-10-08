---
title: Weekly Update - Apr 10th, 2015
author:  Giovanny Gioyik (@Gioyik) & Julian Duque (@julianduque)
date: 2015-04-10T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-04-10
layout: blog-post.hbs
---

<!--
# io.js 1.6.4 release
-->

## io.js 1.6.4 リリース

<!--
This week we had one io.js release [v1.6.4](https://iojs.org/dist/v1.6.4/), complete changelog can be found [on GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).
-->

私たちは io.js の [v1.6.4](https://iojs.org/dist/v1.6.4/) を今週リリースしました。完全なチェンジログは [GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md) で確認できます。

<!--
### Notable changes
-->

### 主な変更点

#### 1.6.4

<!--
* **npm**: upgrade npm to 2.7.5. See [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v275-2015-03-26) for details. Includes two important security fixes.
* **openssl**: preliminary work has been done for an upcoming upgrade to OpenSSL 1.0.2a [#1325](https://github.com/iojs/io.js/pull/1325) (Shigeki Ohtsu). See [#589](https://github.com/iojs/io.js/issues/589) for additional details.
* **timers**: a minor memory leak when timers are unreferenced was fixed, alongside some related timers issues [#1330](https://github.com/iojs/io.js/pull/1330) (Fedor Indutny). This appears to have fixed the remaining leak reported in [#1075](https://github.com/iojs/io.js/issues/1075).
* **android**: it is now possible to compile io.js for Android and related devices [#1307](https://github.com/iojs/io.js/pull/1307) (Giovanny Andres Gongora Granada).
-->

* **npm**: バージョンを`2.7.5`にアップデート。2つの重要なセキュリティフィックスが含まれています。詳細は [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v275-2015-03-26) を参照してください。
* **openssl**: バージョン`1.0.2a`へのアップデートのための準備作業が [#1325](https://github.com/iojs/io.js/pull/1325)(Shigeki Ohtsu) にて行われました。詳細は [#589](https://github.com/iojs/io.js/issues/589) を参照してください。
* **timers**: 非参照のtimersが小さいメモリリークを引き起こす問題は、いくつかのtimers関連の問題と並んで修正されました [#1330](https://github.com/iojs/io.js/pull/1330)(Fedor Indutny)。これにより、[#1075](https://github.com/iojs/io.js/issues/1075) にて報告されていたメモリリークの問題も解決しました。
* **android**: Android、及び関連するデバイスのためにio.jsのコンパイルが可能になりました [#1307](https://github.com/iojs/io.js/pull/1307)(Giovanny Andres Gongora Granada)。

<!--
### Known issues
-->

### 既知の問題

<!--
* Some problems with unreferenced timers running during `beforeExit` are still to be resolved. See [#1264](https://github.com/iojs/io.js/issues/1264).
* Surrogate pair in REPL can freeze terminal [#690](https://github.com/iojs/io.js/issues/690)
* Not possible to build io.js as a static library [#686](https://github.com/iojs/io.js/issues/686)
* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/iojs/io.js/issues/760) and fix in [#774](https://github.com/iojs/io.js/issues/774)
* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion [#894](https://github.com/iojs/io.js/issues/894)
-->

* `beforeExit` が実行されている最中の非参照のtimersに起因するいくつかの問題は、まだ解決されていません。詳細は [#1264](https://github.com/iojs/io.js/issues/1264) を参照して下さい。
* REPL 内のサロゲートペアがターミナルのフリーズを引き起こすことがあります。 [#690](https://github.com/iojs/io.js/issues/690)
* 静的ライブラリとしてio.jsをビルドすることができません。 [#686](https://github.com/iojs/io.js/issues/686)
* `process.send()` はドキュメントに記述されている通り、本来は同期的に実行されるはずですが、`1.0.2` にて発生した不具合により非同期的に呼び出されてしまうようになりました。詳細は [#760](https://github.com/iojs/io.js/issues/760) を、修正については [#774](https://github.com/iojs/io.js/issues/774) を参照して下さい。
* `dns.setServers()` を呼び出している間の DNS クエリが、進行中にアサーションに失敗してプロセスをクラッシュさせることがあります。[#894](https://github.com/iojs/io.js/issues/894)

<!--
### Community Updates
-->

## コミュニティアップデート

<!--
* [Node Foundation dev policy draft is [here](https://github.com/jasnell/dev-policy)
* ARMv8 / ARM64 [support](https://twitter.com/rvagg/status/586050873349939201) on io.js
* Continued work on a new dev policy for [node.js/io.js](https://github.com/jasnell/dev-policy)
* TC call from [Wednesday](https://www.youtube.com/watch?v=OjlK8k10oyo)
-->

* Node Foundationの開発ポリシーの草案は[こちら](https://github.com/jasnell/dev-policy)
* io.jsの ARMv8 / ARM64 のサポートについては[こちら](https://twitter.com/rvagg/status/586050873349939201)
* 新しい開発ポリシーの策定については [こちら](https://github.com/jasnell/dev-policy)
* 水曜日に行われたTCミーティングについては [こちら](https://www.youtube.com/watch?v=OjlK8k10oyo)

<!--
### Upcoming Events
-->

## 今後開催されるイベント
<!--
* [NodeConf Adventure](http://nodeconf.com/) for June 11th - 14th at Walker Creek Ranch, CA
* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State
* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
* [nodeSchool Tokyo](http://nodejs.connpass.com/event/13182/) will be held in April 12th at Tokyo, Japan
-->

* [NodeConf Adventure](http://nodeconf.com/) が11-14日にウォーカークリークランチにて開催されます。
* [CascadiaJS](http://2015.cascadiajs.com/) のチケットが販売中です。7月8-10日にワシントン州にて開催されます。
* [NodeConf EU](http://nodeconf.eu/) のチケットが販売中です。9月6-9日にアイルランドのウォーターフォードにて開催されます。
* [NodeSchool Tokyo](http://nodejs.connpass.com/event/13182/) が4月12日に東京で開催されます。

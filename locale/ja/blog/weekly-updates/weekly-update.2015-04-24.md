---
title: Weekly Update - Apr 24th, 2015
author:  Giovanny Gioyik (@Gioyik)
date: 2015-04-24T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-04-24
layout: blog-post.hbs
---

<!--
# io.js 1.8.1 release
-->

## io.js 1.8.1 リリース

<!--
This week we had one io.js release [v1.8.1](https://iojs.org/dist/v1.8.1/), complete changelog can be found [on GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).
-->

今週は io.js の [v1.8.1](https://iojs.org/dist/v1.8.1/) のリリースを行いました。完全なチェンジログは [GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md) で確認できます。

<!--
### Notable changes
-->

### 主な変更点

<!--
* **NOTICE**: Skipped v1.8.0 due to problems with release tooling.
  See [#1436](https://github.com/iojs/io.js/issues/1436) for details.
* **build**: Support for building io.js as a static library (Marat Abdullin) [#1341](https://github.com/iojs/io.js/pull/1341)
* **deps**: Upgrade openssl to 1.0.2a (Shigeki Ohtsu) [#1389](https://github.com/iojs/io.js/pull/1389)
  * Users should see performance improvements when using the crypto API.
  See [here](https://github.com/iojs/io.js/wiki/Crypto-Performance-Notes-for-OpenSSL-1.0.2a-on-iojs-v1.8.0)
  for details.
* **npm**: Upgrade npm to 2.8.3. See the [release notes](https://github.com/npm/npm/releases/tag/v2.8.3) for details. Includes improved git support.
* **src**: Allow multiple arguments to be passed to process.nextTick (Trevor Norris) [#1077](https://github.com/iojs/io.js/pull/1077)
* **module**: The interaction of `require('.')` with `NODE_PATH` has been restored and deprecated. This functionality
will be removed at a later point. (Roman Reiss) [#1363](https://github.com/iojs/io.js/pull/1363)
-->

* **注意**: v1.8.0 はリリースツールの問題によってスキップされました。詳細は [#1436](https://github.com/iojs/io.js/issues/1436) を参照してください。
* **build**: io.js を静的なライブラリとしてビルドするサポート (Marat Abdullin) [#1341](https://github.com/iojs/io.js/pull/1341)
* **deps**: openssl を 1.0.2a にアップグレード (Shigeki Ohtsu) [#1389](https://github.com/iojs/io.js/pull/1389)
  * crypto API を使用する際にパフォーマンスの改善がみられます。
  [こちら](https://github.com/iojs/io.js/wiki/Crypto-Performance-Notes-for-OpenSSL-1.0.2a-on-iojs-v1.8.0) をご覧ください。
* **npm**: npm を 2.8.3 にアップグレード。詳細については [release notes](https://github.com/npm/npm/releases/tag/v2.8.3) をご覧ください。 改善された git のサポートを含みます。
* **src**: process.nextTick に複数の引数を渡すことを許可 (Trevor Norris) [#1077](https://github.com/iojs/io.js/pull/1077)
* **module**: `require('.')` と `NODE_PATH` の間の相互作用は再構築され、反対されています。この機能性は後に削除されるでしょう。 (Roman Reiss) [#1363](https://github.com/iojs/io.js/pull/1363)



<!--
### Known issues
-->

### 既知の問題

<!--
* Some problems with unreferenced timers running during `beforeExit` are still to be resolved. See [#1264](https://github.com/iojs/io.js/issues/1264).
* Surrogate pair in REPL can freeze terminal [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/iojs/io.js/issues/760) and fix in [#774](https://github.com/iojs/io.js/issues/774)
* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion [#894](https://github.com/iojs/io.js/issues/894)
* `url.resolve` may transfer the auth portion of the url when resolving between two full hosts, see [#1435](https://github.com/iojs/io.js/issues/1435).
* readline: split escapes are processed incorrectly, see [#1403](https://github.com/iojs/io.js/issues/1403)
-->

* `beforeExit` が実行されている最中の非参照のtimersに起因するいくつかの問題は、まだ解決されていません。詳細は [#1264](https://github.com/iojs/io.js/issues/1264) を参照して下さい。
* REPL 内のサロゲートペアがターミナルのフリーズを引き起こすことがあります。 [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` はドキュメントに記述されている通り、本来は同期的に実行されるはずですが、`1.0.2` にて発生した不具合により非同期的に呼び出されてしまうようになりました。詳細は [#760](https://github.com/iojs/io.js/issues/760) を、修正については [#774](https://github.com/iojs/io.js/issues/774) を参照して下さい。
* `dns.setServers()` を呼び出している間の DNS クエリが、進行中にアサーションに失敗してプロセスをクラッシュさせることがあります。[#894](https://github.com/iojs/io.js/issues/894)
* `url.resolve` は2つの完全なホストを解決しようとした際に url の auth の部分を写す可能性があります。詳細は [#1435](https://github.com/iojs/io.js/issues/1435) を参照してください。
* readline: エスケープ処理の分割が正しく動作しません。詳細は [#1403](https://github.com/iojs/io.js/issues/1403) を参照してください。

<!--
### Community Updates
-->

## コミュニティアップデート

<!--
* Fedor Indutny opened discussion about removing TLS `newSession` and `resumeSession` event. [iojs/io.js#1462](https://github.com/iojs/io.js/issues/1462)
* Proposal to change the C HTTP parser JS HTTP parser [here](https://github.com/iojs/io.js/pull/1457)
* NPM founder talks about io.js at [InfoWorld](http://www.infoworld.com/article/2910594/node-js/npm-founder-foresees-merger-node-js-io-js.html)
* Proposal to add mikeal, mscdex, shigeki as new TC members. [iojs/io.js#1483](https://github.com/iojs/io.js/issues/1483#issuecomment-95128140)
-->

* Fedor Indutny は TLS の `newSession` と `resumeSession` イベントを削除することについての議論を開始しました。 [iojs/io.js#1462](https://github.com/iojs/io.js/issues/1462)
* C HTTP parser を JS HTTP parser に変更する提案は[こちら](https://github.com/iojs/io.js/pull/1457)。
* NPM の設立者が io.js について語っています。 [InfoWorld](http://www.infoworld.com/article/2910594/node-js/npm-founder-foresees-merger-node-js-io-js.html)
* mikeal, mscdex, shigeki をTC(技術委員会)の新しいメンバーに加える提案。 [iojs/io.js#1483](https://github.com/iojs/io.js/issues/1483#issuecomment-95128140)

<!--
### Upcoming Events
-->

## 今後開催されるイベント

<!--
* [JSConf Uruguay](http://jsconf.uy) tickets are on sale, April 24th & 25th at Montevideo, Uruguay
* [NodeConf Adventure](http://nodeconf.com/) tickets are on sale, June 11th - 14th at Walker Creek Ranch, CA
* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State
* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
-->

* [JSConf Uruguay](http://jsconf.uy) のチケットが販売中です。4月24-25日にウルグアイのモンテビデオにて開催されます。
* [NodeConf Adventure](http://nodeconf.com/) が6月11-14日にカリフォルニアのウォーカークリークランチにて開催されます。
* [CascadiaJS](http://2015.cascadiajs.com/) のチケットが販売中です。7月8-10日にワシントン州にて開催されます。
* [NodeConf EU](http://nodeconf.eu/) のチケットが販売中です。9月6-9日にアイルランドのウォーターフォードにて開催されます。

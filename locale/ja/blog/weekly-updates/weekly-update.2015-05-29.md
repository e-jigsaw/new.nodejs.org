---
title: Weekly Update - May 29th, 2015
author: Giovanny Gioyik (@Gioyik)
date: 2015-05-29T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-05-29
layout: blog-post.hbs
---

<!--
# io.js 2.2 releases
-->

## io.js 2.2 リリース

<!--
This week we had two io.js releases [v2.2.0](https://iojs.org/dist/v2.2.0/) and [v2.2.1](https://iojs.org/dist/v2.2.1/), complete changelog can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).
-->

今週は [v2.2.0](https://iojs.org/dist/v2.2.0/) と [v2.2.1](https://iojs.org/dist/v2.2.1/) の2回 io.js のリリースをしました。完全なチェンジログは [GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md) で見れます。

<!--
### Notable changes
-->

### 主な変更点

<!--
#### v2.2.0
-->

#### v2.2.0

<!--
* **node**: Speed-up `require()` by replacing usage of `fs.statSync()` and `fs.readFileSync()` with internal variants that are faster for this use-case and do not create as many objects for the garbage collector to clean up. The primary two benefits are: significant increase in application start-up time on typical applications and better start-up time for the debugger by eliminating almost all of the thousands of exception events. (Ben Noordhuis) [#1801](https://github.com/nodejs/io.js/pull/1801).
* **node**: Resolution of pre-load modules (`-r` or `--require`) now follows the standard `require()` rules rather than just resolving paths, so you can now pre-load modules in node_modules. (Ali Ijaz Sheikh) [#1812](https://github.com/nodejs/io.js/pull/1812).
* **npm**: Upgraded npm to v2.11.0. New hooks for `preversion`, `version`, and `postversion` lifecycle events, some SPDX-related license changes and license file inclusions. See the [release notes](https://github.com/npm/npm/releases/tag/v2.11.0) for full details.
-->

* **node**: `fs.statSync()` と `fs.readFileSync()` を使用していた箇所をこのユースケースのために改善された内部変数に置換しました。この変更によって多数のオブジェクトを作らずに済むため、 GC の作業が減らされ、 `require()` が高速化されます。主な2つのメリットはアプリケーションの起動時間の改善と数千もの例外イベントが削除されることにより、デバッガーの起動時間が改善されます。(Ben Noordhuis) [#1801](https://github.com/nodejs/io.js/pull/1801)
* **node**: プリロードモジュール(`-r` または `--require`)は標準の `require()` のパス解決ルールに従って解決されるので、`node_modules` からプリロードできるようになりました。 (Ali Ijaz Sheikh) [#1812](https://github.com/nodejs/io.js/pull/1812)
* **npm**: npm を v2.11.0 にアップグレードしました。新しいフックとしてライフサイクルイベントの `preversion`, `version` と `postversion` が追加されました。いくつかの SPDX-related ライセンスが変更され、ライセンスファイルが含まれるようになりました。詳細は[リリースノート](https://github.com/npm/npm/releases/tag/v2.11.0)をご覧ください。

<!--
#### v2.2.1
-->

#### v2.2.1

<!--
* **http**: reverts the removal of an undocumented `client` property on client connections, this property is being used in the wild, most notably by [request](https://github.com/request/request) which is used by npm. (Michaël Zasso) [#1852](https://github.com/nodejs/io.js/pull/1852).
-->

* **http**: 削除されたドキュメント化されていないクライアントコネクションの `client` プロパティを元に戻しました。このプロパティは様々な箇所で使われていました。特筆するべきモジュールは [request](https://github.com/request/request) です。このモジュールは npm でも使われています。(Michaël Zasso) [#1852](https://github.com/nodejs/io.js/pull/1852)

<!--
### Known issues
-->

### 既知の問題

<!--
See https://github.com/nodejs/io.js/labels/confirmed-bug for complete and current list of known issues.
-->

現在の完全な既知の問題リストは https://github.com/nodejs/io.js/labels/confirmed-bug を参照してください。

<!--
* Some problems with unreferenced timers running during `beforeExit` are still to be resolved. See [#1264](https://github.com/nodejs/io.js/issues/1264).
* Surrogate pair in REPL can freeze terminal [#690](https://github.com/nodejs/io.js/issues/690)
* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/nodejs/io.js/issues/760) and fix in [#774](https://github.com/nodejs/io.js/issues/774)
* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion [#894](https://github.com/nodejs/io.js/issues/894)
* `url.resolve` may transfer the auth portion of the url when resolving between two full hosts, see [#1435](https://github.com/nodejs/io.js/issues/1435).
-->

* `beforeExit` が実行されている最中の非参照のtimersに起因するいくつかの問題は、まだ解決されていません。詳細は [#1264](https://github.com/nodejs/io.js/issues/1264) を参照して下さい。
* REPL 内のサロゲートペアがターミナルのフリーズを引き起こすことがあります。 [#690](https://github.com/nodejs/io.js/issues/690)
* `process.send()` はドキュメントに記述されている通り、本来は同期的に実行されるはずですが、`1.0.2` にて発生した不具合により非同期的に呼び出されてしまうようになりました。詳細は [#760](https://github.com/nodejs/io.js/issues/760) を、修正については [#774](https://github.com/nodejs/io.js/issues/774) を参照して下さい。
* `dns.setServers()` を呼び出している間の DNS クエリが、進行中にアサーションに失敗してプロセスをクラッシュさせることがあります。[#894](https://github.com/nodejs/io.js/issues/894)
* `url.resolve` は2つの完全なホストを解決しようとした際に url の auth の部分を移動する可能性があります。詳細は [#1435](https://github.com/nodejs/io.js/issues/1435) を参照してください。

<!--
### Community Updates
-->

## コミュニティより

<!--
* [Schism and Reconciliation](https://nodesource.com/blog/was-this-trip-really-necessary) in the Node Community by Rod Vagg.
* First Node TSC Meeting available on [SoundCloud](https://soundcloud.com/node-foundation/tsc-meeting-2015-05-27).
* io.js have got a new Benchmarking Working Group [nodejs/benchmarking#1](https://github.com/nodejs/benchmarking/issues/1).
* Blog post about iojs + node.js under Node Foundation by [nodejs.com](http://blog.nodejs.org/2015/05/15/the-nodejs-foundation-benefits-all/).
* io.js implements new [`good first contribution`](https://github.com/nodejs/io.js/labels/good%20first%20contribution) tag for new contributors.
* Blog post from [TheNewStack](http://thenewstack.io/io-js-and-node-js-have-united-and-thats-a-good-thing/) about iojs and node.js new relation.
* Oliver Zeigermann created a [repo](https://github.com/DJCordhose/ecmascript-2015-iojs) about ES6 and iojs implementation.
-->

* Rod Vagg は Node コミュニティの分裂と和解の[記事](https://nodesource.com/blog/was-this-trip-really-necessary)を書きました。
* 最初の Node TSC ミーティングは [SoundCloud](https://soundcloud.com/node-foundation/tsc-meeting-2015-05-27) で聞くことができます。
* io.js は新しい Benchmarking Working Group を創設しました: [nodejs/benchmarking#1](https://github.com/nodejs/benchmarking/issues/1)。
* Node Foundation 下の io.js + node.js についての[記事](http://blog.nodejs.org/2015/05/15/the-nodejs-foundation-benefits-all/)。
* io.js は新しいコントリビュータに向けて [`good first contribution`](https://github.com/nodejs/io.js/labels/good%20first%20contribution) タグを実装しました。
* [TheNewStack](http://thenewstack.io/io-js-and-node-js-have-united-and-thats-a-good-thing/) にて io.js と node.js の新しい関係について記事が投稿されました。
* Oliver Zeigermann は ES6 と io.js の実装についての[リポジトリ](https://github.com/DJCordhose/ecmascript-2015-iojs) を作成しました。

<!--
### Upcoming Events
-->

## 今後開催されるイベント

<!--
* [NodeConf Adventure](http://nodeconf.com/) tickets are on sale, June 11th - 14th at Walker Creek Ranch, CA
* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State
* [BrazilJS Conf](http://braziljs.com.br/) tickets are on sale, August 21st - 22nd at Shopping Center BarraShoppingSul
* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
-->

* [NodeConf Adventure](http://nodeconf.com/) のチケットが販売中です。6月11-14日にカリフォルニアのウォーカークリークランチにて開催されます。
* [CascadiaJS](http://2015.cascadiajs.com/) のチケットが販売中です。7月8-10日にワシントン州にて開催されます。
* [BrazilJS Conf](http://braziljs.com.br/) のチケットが販売中です。8月21-22日にリオ・グランデ・ド・スール州のBarra Shopping Sulで開催されます。
* [NodeConf EU](http://nodeconf.eu/) のチケットが販売中です。9月6-9日にアイルランドのウォーターフォードにて開催されます。

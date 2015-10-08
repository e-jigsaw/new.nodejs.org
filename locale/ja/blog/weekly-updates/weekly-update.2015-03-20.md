---
title: Weekly Update - Mar 20th, 2015
author: Julian Duque (julianduque)
date: 2015-03-20T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-03-20
layout: blog-post.hbs
---

<!--
# io.js 1.6 release
This week we had a two io.js releases [v1.6.1](https://iojs.org/dist/v1.6.1/) and  [v1.6.0](https://iojs.org/dist/v1.6.0/), complete changelog can be found [on GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).
-->

## io.js 1.6 リリース

我々は今週 [v1.6.1](https://iojs.org/dist/v1.6.1/) と [v1.6.0](https://iojs.org/dist/v1.6.0/) の2つをリリースしました。完全なチェンジログは [GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md) にて。

<!--
### Notable changes
-->

### 主な変更点

#### 1.6.1

<!--
* **path**: New type-checking on `path.resolve()` [#1153](https://github.com/iojs/io.js/pull/1153) uncovered some edge-cases being relied upon in the wild, most notably `path.dirname(undefined)`. Type-checking has been loosened for `path.dirname()`, `path.basename()`, and `path.extname()` (Colin Ihrig) [#1216](https://github.com/iojs/io.js/pull/1216).
* **querystring**: Internal optimizations in `querystring.parse()` and `querystring.stringify()` [#847](https://github.com/iojs/io.js/pull/847) prevented `Number` literals from being properly converted via `querystring.escape()` [#1208](https://github.com/iojs/io.js/issues/1208), exposing a blind-spot in the test suite. The bug and the tests have now been fixed (Jeremiah Senkpiel) [#1213](https://github.com/iojs/io.js/pull/1213).
-->

* **path**: `path.resolve()` に新しいタイプチェックが追加され([#1153](https://github.com/iojs/io.js/pull/1153))、`path.dirname(undefined)` のようなエッジケースが発見されました。タイプチェックは `path.dirname()`, `path.basename()`, そして `path.extname()` のために緩められることになりました。(Colin Ihrig) [#1216](https://github.com/iojs/io.js/pull/1216)
* **querystring**: `querystring.parse()` と `querystring.stringify()` の処理最適化が ([#847](https://github.com/iojs/io.js/pull/847)) によって行われました。しかしその最適化は `querystring.escape()` によって変換された `Number` リテラルを処理しないというバグが発見されました。テストケースの盲点が露呈してしまいました。このバグとテストは修正済です。(Jeremiah Senkpiel) [#1213](https://github.com/iojs/io.js/pull/1213)

#### 1.6.0

<!--
* **node**: a new `-r` or `--require` command-line option can be used to pre-load modules at start-up (Ali Ijaz Sheikh) [#881](https://github.com/iojs/io.js/pull/881).
* **querystring**: `parse()` and `stringify()` are now faster (Brian White) [#847](https://github.com/iojs/io.js/pull/847).
* **http**: the `http.ClientRequest#flush()` method has been deprecated and replaced with `http.ClientRequest#flushHeaders()` to match the same change now in Node.js v0.12 as per [joyent/node#9048](https://github.com/joyent/node/pull/9048) (Yosuke Furukawa) [#1156](https://github.com/iojs/io.js/pull/1156).
* **net**: allow `server.listen()` to accept a `String` option for `port`, e.g. `{ port: "1234" }`, to match the same option being accepted in `net.connect()` as of [joyent/node#9268](https://github.com/joyent/node/pull/9268) (Ben Noordhuis) [#1116](https://github.com/iojs/io.js/pull/1116).
* **tls**: further work on the reported memory leak although there appears to be a minor leak remaining for the use-case in question, track progress at [#1075](https://github.com/iojs/io.js/issues/1075).
* **v8**: backport a fix for an integer overflow when `--max_old_space_size` values above `4096` are used (Ben Noordhuis) [#1166](https://github.com/iojs/io.js/pull/1166).
* **platforms**: the io.js CI system now reports passes on **FreeBSD** and **SmartOS** (_Solaris_).
* **npm**: upgrade npm to 2.7.1. See [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v271-2015-03-05) for details.
-->

* **node**: 新しいコマンドラインオプションの `--require` もしくは `-r` が追加され、スタート時にモジュールをプリロードできます。(Ali Ijaz Sheikh) [#881](https://github.com/iojs/io.js/pull/881)
* **querystring**: `parse()` と `stringify()` が高速化されました。(Brian White) [#847](https://github.com/iojs/io.js/pull/847)
* **http**: `http.ClientRequest#flush()` メソッドが非推奨となり、Node.js v0.12([joyent/node#9048](https://github.com/joyent/node/pull/9048)) に従って `http.ClientRequest#flushHeaders()` に置き換えられました。(Yosuke Furukawa) [#1156](https://github.com/iojs/io.js/pull/1156)
* **net**: `server.listen()` において `port` オプションを `String` でも許可しました。例: `{ port: "1234" }` 同じオプションが [joyent/node#9268](https://github.com/joyent/node/pull/9268) のように `net.connect()` でも受け入れられます。(Ben Noordhuis) [#1116](https://github.com/iojs/io.js/pull/1116)
* **tls**: 残っているマイナーなユースケースのメモリリーク問題について取り組んでいます。進捗は [#1075](https://github.com/iojs/io.js/issues/1075) にて。
* **v8**: `--max_old_space_size` を `4096` にしたときの integer がオーバーフローするバックポートを修正しました。(Ben Noordhuis) [#1166](https://github.com/iojs/io.js/pull/1166)
* **platforms**: io.js の CI システムは **FreeBSD** と **SmartOS** (_Solaris_) でパスしたことを報告しました。
* **npm**: npm のバージョンを 2.7.1 にアップグレードしました。詳細は  [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v271-2015-03-05) にて。

<!--
### Known Issues
-->

### 既知の問題

<!--
* Possible remaining TLS-related memory leak(s), details at [#1075](https://github.com/iojs/io.js/issues/1075).
* Surrogate pair in REPL can freeze terminal [#690](https://github.com/iojs/io.js/issues/690)
* Not possible to build io.js as a static library [#686](https://github.com/iojs/io.js/issues/686)
* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/iojs/io.js/issues/760) and fix in [#774](https://github.com/iojs/io.js/issues/774)
* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion [#894](https://github.com/iojs/io.js/issues/894)
-->

* TLS 関連のメモリリークが依然として発生することがあります。詳細は [#1075](https://github.com/iojs/io.js/issues/1075) にて。
* REPL 内のサロゲートペアがターミナルをフリーズさせることが可能です。[#690](https://github.com/iojs/io.js/issues/690)
* 静的ライブラリとして io.js をビルドすることができません。[#686](https://github.com/iojs/io.js/issues/686)
* child_process から生成された際の `process.send()` は[ドキュメントに記述されている](https://iojs.org/api/child_process.html#child_process_child_send_message_sendhandle)通り、本来は同期的に実行されるはずですが、1.0.2 によって発生した不具合により非同期的に呼び出されてしまうようになりました。詳細は [#760](https://github.com/iojs/io.js/issues/760) そして issue [#774](https://github.com/iojs/io.js/issues/774) で修正中です。
* `dns.setServers()` を呼び出す間の DNS クエリが進行中にアサーションに失敗してプロセスをクラッシュさせることがあります。[#894](https://github.com/iojs/io.js/issues/894)

<!--
# Community Updates
-->

## コミュニティアップデート

<!--
* browserify supports io.js, you can check the announcement [here](https://twitter.com/yosuke_furukawa/status/577150547850969088)
* express.js added [support](https://github.com/strongloop/express/commit/165660811aa9ba5f3733a7b033894f3d9a9c5e60) to io.js
* Over the last two weeks we got access to hardware from Joyent and upstreamed a patch to V8 so we got io.js building. After that we worked on passing tests for both [SmartOS](https://github.com/iojs/build/pull/64) and [FreeBSD](https://github.com/iojs/io.js/pull/1167) which as of two days ago now pass, this was thanks to the amazing work of the build team and [Johan Bergström](https://github.com/jbergstroem)
* [Petka Antonov](https://github.com/petkaantonov) is proposing a workers implementation in io.js under an experimental flag, you can join the discussion [here](https://github.com/iojs/io.js/pull/1159)
* io.js [upgraded](https://github.com/iojs/io.js/pull/1206) openssl to `1.0.1m`
-->

* browserify が io.js をサポートしはじめました。アナウンスは[こちら](https://twitter.com/yosuke_furukawa/status/577150547850969088)です。
* express.js は io.js の[サポート](https://github.com/strongloop/express/commit/165660811aa9ba5f3733a7b033894f3d9a9c5e60)を追加しました
* この2週間で我々は Joyent とその上流の V8 のパッチからのハードウェアのアクセスを得たので、io.js のビルドを得ました。この後、我々は [SmartOS](https://github.com/iojs/build/pull/64) と [FreeBSD](https://github.com/iojs/io.js/pull/1167) でテストをパスさせる作業をし、2日前にこれをパスしました。この素晴らしい偉業を成し遂げたビルドチームと [Johan Bergström](https://github.com/jbergstroem) に感謝を。
* [Petka Antonov](https://github.com/petkaantonov) は workers の実装を experimental フラグの下に提案しました。[こちら](https://github.com/iojs/io.js/pull/1159)で議論に参加できます。
* io.js は openssl を `1.0.1m` に[アップグレード](https://github.com/iojs/io.js/pull/1206)しました。

<!--
# Upcoming Events
-->

## 今後開催されるイベント

<!--
* [NodeConf](http://nodeconf.com/) tickets are on sale, June 8th and 9th at Oakland, CA and NodeConf Adventure for June 11th - 14th at Walker Creek Ranch, CA
* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State
* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
-->

* [NodeConf](http://nodeconf.com/) のチケットが販売中です。6月8-9日にカルフォルニアのオークランドにて開催され、11-14日は NodeConf Adventure がウォーカークリークランチにて開催されます。
* [CascadiaJS](http://2015.cascadiajs.com/) のチケットも販売中です。7月8-10日にワシントン州にて開催されます。
* [NodeConf EU](http://nodeconf.eu/) のチケットも販売中です。9月6-9日にアイルランドのウォーターフォードにて開催されます。

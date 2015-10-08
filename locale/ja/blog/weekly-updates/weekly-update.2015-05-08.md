---
title: Weekly Update - May 8th, 2015
author: Giovanny Gioyik (@Gioyik) & Daijiro Wachi (@watilde)
date: 2015-05-08T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-05-08
layout: blog-post.hbs
---

<!--
# io.js 2.0 releases
This week we had two io.js releases [v2.0.0](https://iojs.org/dist/v2.0.0/) and [v2.0.1](https://iojs.org/dist/v2.0.1/), complete changelog can be found [on GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).
-->

## io.js 2.0 リリース

今週は、[v2.0.0](https://iojs.org/dist/v2.0.0/)と[v2.0.1](https://iojs.org/dist/v2.0.1/)のリリースを行いました。完全なチェンジログは、[GitHub](https://github.com/iojs/io.js/blob/master/CHANGELOG.md)で確認できます。

<!--
### Notable changes
-->

### 主な変更点

<!--
#### 2.0.1
* **async_wrap**: (Trevor Norris) [#1614](https://github.com/iojs/io.js/pull/1614)
  - it is now possible to filter by providers
  - bit flags have been removed and replaced with method calls on the binding object
  - _note that this is an unstable API so feature additions and breaking changes won't change io.js semver_
* **libuv**: resolves numerous io.js issues:
  - [#862](https://github.com/iojs/io.js/issues/862) prevent spawning child processes with invalid stdio file descriptors
  - [#1397](https://github.com/iojs/io.js/issues/1397) fix EPERM error with fs.access(W_OK) on Windows
  - [#1621](https://github.com/iojs/io.js/issues/1621) build errors associated with the bundled libuv
  - [#1512](https://github.com/iojs/io.js/issues/1512) should properly fix Windows termination errors
* **addons**: the `NODE_DEPRECATED` macro was causing problems when compiling addons with older compilers, this should now be resolved (Ben Noordhuis) [#1626](https://github.com/iojs/io.js/pull/1626)
* **V8**: upgrade V8 from 4.2.77.18 to 4.2.77.20 with minor fixes, including a bug preventing builds on FreeBSD
-->

#### 2.0.1

* **async_wrap**: (Trevor Norris) [#1614](https://github.com/iojs/io.js/pull/1614)
  - プロバイダを用いてフィルタリングすることが可能になりました
  - ビットフラグは削除され、バインドされたオブジェクトのメソッド呼び出しに置き換えられました
  - *注記: これは不安定なAPIなので、機能追加や互換性のない変更があってもio.jsのセマンティックバージョンの更新はしないつもりです*
* **libuv**: 多数のissueを解決:
  - [#862](https://github.com/iojs/io.js/issues/862) 無効な標準入力ファイルの記述子による子プロセスの生成を防ぐ修正をしました
  - [#1397](https://github.com/iojs/io.js/issues/1397) Windows で fs.access(W_OK) をした際に発生していたEPERMのエラーを修正しました
  - [#1621](https://github.com/iojs/io.js/issues/1621) バンドルされている libuv のタグを修正しました
  - [#1512](https://github.com/iojs/io.js/issues/1512) Windowsで処理の終了時に発生するエラーを修正しました
* **addons**: `NODE_DEPRECATED`マクロは、コンパイラのバージョンが古いことが原因でアドオンのコンパイルに問題が発生していましたが、解決しました (Ben Noordhuis) [#1626](https://github.com/iojs/io.js/pull/1626)
* **V8**: バージョンを4.2.77.18から4.2.77.20に更新。いくつかの小さい改善と、FreeBSDでビルドする際のバグを防ぐ改善が含まれています

<!--
#### 2.0.0
* **crypto**: significantly reduced memory usage for TLS (Fedor Indutny & Сковорода Никита Андреевич) [#1529](https://github.com/iojs/io.js/pull/1529)
* **net**: `socket.connect()` now accepts a `'lookup'` option for a custom DNS resolution mechanism, defaults to `dns.lookup()` (Evan Lucas) [#1505](https://github.com/iojs/io.js/pull/1505)
* **npm**: Upgrade npm to 2.9.0. See the [v2.8.4](https://github.com/npm/npm/releases/tag/v2.8.4) and [v2.9.0](https://github.com/npm/npm/releases/tag/v2.9.0) release notes for details. Notable items:
  - Add support for default author field to make `npm init -y` work without user-input (@othiym23) [npm/npm/d8eee6cf9d](https://github.com/npm/npm/commit/d8eee6cf9d2ff7aca68dfaed2de76824a3e0d9af)
  - Include local modules in `npm outdated` and `npm update` (@ArnaudRinquin) [npm/npm#7426](https://github.com/npm/npm/issues/7426)
  - The prefix used before the version number on `npm version` is now configurable via `tag-version-prefix` (@kkragenbrink) [npm/npm#8014](https://github.com/npm/npm/issues/8014)
* **os**: `os.tmpdir()` is now cross-platform consistent and will no longer returns a path with a trailling slash on any platform (Christian Tellnes) [#747](https://github.com/iojs/io.js/pull/747)
* **process**:
  - `process.nextTick()` performance has been improved by between 2-42% across the benchmark suite, notable because this is heavily used across core (Brian White) [#1571](https://github.com/iojs/io.js/pull/1571)
  - New `process.geteuid()`, `process.seteuid(id)`, `process.getegid()` and `process.setegid(id)` methods allow you to get and set effective UID and GID of the process (Evan Lucas) [#1536](https://github.com/iojs/io.js/pull/1536)
* **repl**:
  - REPL history can be persisted across sessions if the `NODE_REPL_HISTORY_FILE` environment variable is set to a user accessible file, `NODE_REPL_HISTORY_SIZE` can set the maximum history size and defaults to `1000` (Chris Dickinson) [#1513](https://github.com/iojs/io.js/pull/1513)
  - The REPL can be placed in to one of three modes using the `NODE_REPL_MODE` environment variable: `sloppy`, `strict` or `magic` (default); the new `magic` mode will automatically run "strict mode only" statements in strict mode (Chris Dickinson) [#1513](https://github.com/iojs/io.js/pull/1513)
* **smalloc**: the 'smalloc' module has been deprecated due to changes coming in V8 4.4 that will render it unusable
* **util**: add Promise, Map and Set inspection support (Christopher Monsanto) [#1471](https://github.com/iojs/io.js/pull/1471)
* **V8**: upgrade to 4.2.77.18, see the [ChangeLog](https://chromium.googlesource.com/v8/v8/+/refs/heads/4.2.77/ChangeLog) for full details. Notable items:
  - Classes have moved out of staging; the `class` keyword is now usable in strict mode without flags
  - Object literal enhancements have moved out of staging; shorthand method and property syntax is now usable (`{ method() { }, property }`)
  - Rest parameters (`function(...args) {}`) are implemented in staging behind the `--harmony-rest-parameters` flag
  - Computed property names (`{['foo'+'bar']:'bam'}`) are implemented in staging behind the `--harmony-computed-property-names` flag
  - Unicode escapes (`'\u{xxxx}'`) are implemented in staging behind the `--harmony_unicode` flag and the `--harmony_unicode_regexps` flag for use in regular expressions
* **Windows**:
  - Random process termination on Windows fixed (Fedor Indutny)  [#1512](https://github.com/iojs/io.js/issues/1512) / [#1563](https://github.com/iojs/io.js/pull/1563)
  - The delay-load hook introduced to fix issues with process naming (iojs.exe / node.exe) has been made opt-out for native add-ons. Native add-ons should include `'win_delay_load_hook': 'false'` in their binding.gyp to disable this feature if they experience problems . (Bert Belder) [#1433](https://github.com/iojs/io.js/pull/1433)
* **Governance**:
  - Rod Vagg (@rvagg) was added to the Technical Committee (TC)
  - Jeremiah Senkpiel (@Fishrock123) was added to the Technical Committee (TC)
-->

#### 2.0.0

* **crypto**: TLSの使用メモリを削減(Fedor Indutny & Сковорода Никита Андреевич) [#1529](https://github.com/iojs/io.js/pull/1529)
* **net**: カスタムDNSの名前解決を設定するために、`socket.connect()` に `'lookup'` オプションが追加されました。デフォルトは `dns.lookup()` です。(Evan Lucas) [#1505](https://github.com/iojs/io.js/pull/1505)
* **npm**: バージョンを 2.9.0 に更新。詳細は [v2.8.4](https://github.com/npm/npm/releases/tag/v2.8.4) と [v2.9.0](https://github.com/npm/npm/releases/tag/v2.9.0) にあるリリースノートを参照してください。主な変更点:
  - ユーザーの入力を省略して `npm init -y` を実行するために、authorフィールドのデフォルト値を設定可能にしました (@othiym23) [npm/npm/d8eee6cf9d](https://github.com/npm/npm/commit/d8eee6cf9d2ff7aca68dfaed2de76824a3e0d9af)
  - `npm outdated` や `npm update` を実行する際に、ローカルにあるモジュールも含まれるように変更しました (@ArnaudRinquin) [npm/npm#7426](https://github.com/npm/npm/issues/7426)
  - npm versionを実行した際にgitへ追加されるタグのプレフィックスを、`tag-version-prefix` で設定できるようにしました (@kkragenbrink) [npm/npm#8014](https://github.com/npm/npm/issues/8014)
* **os**: `os.tmpdir()` がクロスプラットフォームで一貫した値を返すようになり、どのプラットフォームでも末尾にスラッシュを付けないで返すようになります (Christian Tellnes) [#747](https://github.com/iojs/io.js/pull/747)
* **process**:
  - `process.nextTick()` 全体のベンチマーク環境において、2-42%程度パフォーマンスが改善しました。注目すべきは、コア全体でヘビーに使われているということです。 (Brian White) [#1571](https://github.com/iojs/io.js/pull/1571)
  - `process.geteuid()`, `process.seteuid(id)`, `process.getegid()`, `process.setegid(id)` は、有効なプロセスのUDIとGIDを取得できるように新しくなりました (Evan Lucas) [#1536](https://github.com/iojs/io.js/pull/1536)
* **repl**:
  - REPLのヒストリーは、環境変数の `NODE_REPL_HISTORY_FILE` にユーザーのアクセス可能なファイルが指定されている場合、セッション間で値を共有するようになりました。また、`NODE_REPL_HISTORY_SIZE` にヒストリーの最大サイズを設定することができます。デフォルト値は `1000` です (Chris Dickinson) [#1513](https://github.com/iojs/io.js/pull/1513)
 - 環境変数の `NODE_REPL_MODE` を使うことで、`sloopy`, `strict`, `magic`(デフォルト)の3つのモードを設定できるようになりました。新たに入った `magic` モードは、自動で"strict mode only" ステートメントをstrictモードで実行します。
* **smalloc**: `smalloc` モジュールは、V8の4.4における変更が原因で廃止になりました
* **util**: Promise, Map, Setオブジェクトのconsoleへの出力がわかりやすくなりました (Christopher Monsanto) [#1471](https://github.com/iojs/io.js/pull/1471)
* **V8**: バージョンを 4.2.77.18に更新しました。詳細は [ChangeLog](https://chromium.googlesource.com/v8/v8/+/refs/heads/4.2.77/ChangeLog) を参照して下さい。主な変更点:
  - クラスはステージングの外へ移動しました。`class` キーワードは、フラグのない状態のstrictモードで使用可能です
  - オブジェクトリテラルの拡張機能はステージングの外へ移動しました。省略表記とプロパティの構文は使用可能になりました(`{ method() { }, property }`)
  Rest引数 (`function(...args) {}`)は、ステージングに実装されました。`--harmony-rest-parameters` フラグで有効化します。
  - コンピューテッドプロパティ(`{['foo'+'bar']:'bam'}`)はステージングに実装されました。`--harmony-computed-property-names` フラグで有効化します。
  - Unicodeエスケープ(`'\u{xxxx}'`)はステージングに実装されました。`--harmony_unicode` フラグと `--harmony_unicode_regexps` フラグを有効にすると正規表現の中で利用することが出来ます。
* **Windows**:
  - Windowsの終了時に発生するランダムプロセスが修正されました (Fedor Indutny)  [#1512](https://github.com/iojs/io.js/issues/1512) / [#1563](https://github.com/iojs/io.js/pull/1563)
  - プロセス名(iojs.exe / node.exe)に関する問題を解決するために導入された遅延ロードのフックはネイティブアドオンのためにオプトアウトされました。ネイティブアドオンは、何か問題が発生してこの機能を無効化するには、`'win_delay_load_hook': 'false'` をbinding.gypに含める必要があります。(Bert Belder) [#1433](https://github.com/iojs/io.js/pull/1433)
* **Governance**:
  - Technical Committee (TC) に Rod Vagg (@rvagg) が追加されました
  - Technical Committee (TC) に Jeremiah Senkpiel (@Fishrock123) が追加されました

<!--
### Breaking changes
-->

### 互換性のない変更

<!--
Full details at https://github.com/iojs/io.js/wiki/Breaking-Changes#200-from-1x
-->

詳細はこちらを参照してください https://github.com/iojs/io.js/wiki/Breaking-Changes#200-from-1x

<!--
* V8 upgrade to 4.2, minor changes to C++ API
* `os.tmpdir()` is now cross-platform consistent and will no longer returns a path with a trailling slash on any platform
* While not a *breaking change* the 'smalloc' module has been deprecated in anticipation of it becoming unsupportable with a future upgrade to V8 4.4. See [#1451](https://github.com/iojs/io.js/issues/1451)  for further information.
-->

* V8のバージョンを 4.2 に更新したので、C++ APIにマイナーチェンジが入りました。
* `os.tmpdir()` がクロスプラットフォームで一貫した値を返すようになり、どのプラットフォームでも末尾にスラッシュを付けないで返すようになります
* `smalloc` モジュールは、将来的に行うV8の4.4への更新による影響で廃止となりますが、*互換性のない変更* とは扱いません。 更に詳しい情報は、 [#1451](https://github.com/iojs/io.js/issues/1451) を参照してください。

<!--
_Note: a new version of the 'url' module was reverted prior to release as it was decided the potential for breakage across the npm ecosystem was too great and that more compatibility work needed to be done before releasing it. See [#1602](https://github.com/iojs/io.js/pull/1602) for further information._
-->

*注記:新しい `url` モジュールは、npmのエコシステム全体に多大な影響を与え破損する可能性があることが原因で、リリースをする前に互換性をより担保する必要があったので、リリース前にリバートとなりました。詳細は [#1602](https://github.com/iojs/io.js/pull/1602) を参照してください。*

<!--
### Known issues
-->

### 既知の問題

<!--
See https://github.com/iojs/io.js/labels/confirmed-bug for complete and current list of known issues.
-->

現在の完全な既知の問題リストはこちらを参照してください。 https://github.com/iojs/io.js/labels/confirmed-bug

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
* `url.resolve` は2つの完全なホストを解決しようとした際に url の auth の部分を移動する可能性があります。詳細は [#1435](https://github.com/iojs/io.js/issues/1435) を参照してください。
* readline: エスケープ処理の分割が正しく動作しません。詳細は [#1403](https://github.com/iojs/io.js/issues/1403) を参照してください。

<!--
### Community Updates
-->

### コミュニティより

<!--
* Michael Dawson creates [WG proposal](https://github.com/mhdawson/workgroup-proposals) under the Node Foundation.
* Mikeal Rogers wrote about growing up of io.js [on Medium](https://medium.com/node-js-javascript/growing-up-27d6cc8b7c53).
* CodeSchool [blog post](https://www.codeschool.com/blog/2015/05/08/whats-new-in-io-js-2-0-0/) on what's new in io.js 2.0.
* Node Lead TJ Fontaine [steps back](http://blog.nodejs.org/2015/05/08/next-chapter/) from leader.
-->

* Michael Dawsonは、Node Foundation以下での [WGの提案](https://github.com/mhdawson/workgroup-proposals) を書きました。
* Mikeal Rogersは、[Mediumにて](https://medium.com/node-js-javascript/growing-up-27d6cc8b7c53) io.jsの成長について書きました。
* CodeSchoolは、io.js 2.0の最新情報について [blogの記事](https://www.codeschool.com/blog/2015/05/08/whats-new-in-io-js-2-0-0/) にしました。
* NodeのリーダーTJ Fontaineは、リーダーを [退任](http://blog.nodejs.org/2015/05/08/next-chapter/) します。

<!--
### Upcoming Events
-->

### 今後開催されるイベント

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

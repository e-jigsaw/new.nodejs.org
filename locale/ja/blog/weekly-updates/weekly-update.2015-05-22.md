---
title: Weekly Update - May 22nd, 2015
author: Giovanny Gioyik (@Gioyik) & Yosuke Furukawa (@yosuke-furukawa)
date: 2015-05-22T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-05-22
layout: blog-post.hbs
---

<!--
# io.js 1.8, 2.0 and 2.1 releases
This week we had three io.js releases [v1.8.2](https://iojs.org/dist/v1.8.2/), [v2.0.2](https://iojs.org/dist/v2.0.2/) and [v2.1.0](https://iojs.org/dist/v2.1.0/), complete changelog can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).
-->

## io.js 1.8、2.0、2.1のリリース

今週は、[v1.8.2](https://iojs.org/dist/v1.8.2/)と[v2.0.2](https://iojs.org/dist/v2.0.2/)と[v2.1.0](https://iojs.org/dist/v2.1.0/)の3つのリリースを行いました。完全なチェンジログは、[GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md)で確認できます。

<!--
### Notable changes
-->

### 主な変更点

<!--
#### 1.8.2
-->

#### 1.8.2

<!--
**Maintenance release**
-->

**メンテナンスリリース**

<!--
* **crypto**: significantly reduced memory usage for TLS (Fedor Indutny & Сковорода Никита Андреевич) [#1529](https://github.com/nodejs/io.js/pull/1529)
* **npm**: Upgrade npm to 2.9.0. See the [v2.8.4](https://github.com/npm/npm/releases/tag/v2.8.4) and [v2.9.0](https://github.com/npm/npm/releases/tag/v2.9.0) release notes for details.
-->

* **crypto**: TLSのメモリ使用量を著しく減少させました (Fedor Indutny & Сковорода Никита Андреевич) [#1529](https://github.com/nodejs/io.js/pull/1529)
* **npm**: npmを2.9.0にアップグレードしました。詳細は[v2.8.4](https://github.com/npm/npm/releases/tag/v2.8.4)と[v2.9.0](https://github.com/npm/npm/releases/tag/v2.9.0)のリリースノートを参照してください。

<!--
#### 2.0.2
-->

#### 2.0.2

<!--
* **win,node-gyp**: the delay-load hook for windows addons has now been correctly enabled by default, it had wrongly defaulted to off in the release version of 2.0.0 (Bert Belder) [#1433](https://github.com/nodejs/io.js/pull/1433)
* **os**: `tmpdir()`'s trailing slash stripping has been refined to fix an issue when the temp directory is at '/'. Also considers which slash is used by the operating system. (cjihrig) [#1673](https://github.com/nodejs/io.js/pull/1673)
* **tls**: default ciphers have been updated to use gcm and aes128 (Mike MacCana) [#1660](https://github.com/nodejs/io.js/pull/1660)
* **build**: v8 snapshots have been re-enabled by default as suggested by the v8 team, since prior security issues have been resolved. This should give some perf improvements to both startup and vm context creation. (Trevor Norris) [#1663](https://github.com/nodejs/io.js/pull/1663)
* **src**: fixed preload modules not working when other flags were used before `--require` (Yosuke Furukawa) [#1694](https://github.com/nodejs/io.js/pull/1694)
* **dgram**: fixed `send()`'s callback not being asynchronous (Yosuke Furukawa) [#1313](https://github.com/nodejs/io.js/pull/1313)
* **readline**: emitKeys now keeps buffering data until it has enough to parse. This fixes an issue with parsing split escapes. (Alex Kocharin) [#1601](https://github.com/nodejs/io.js/pull/1601)
* **cluster**: works now properly emit 'disconnect' to `cluster.worker` (Oleg Elifantiev) [#1386](https://github.com/nodejs/io.js/pull/1386)
* **events**: uncaught errors now provide some context (Evan Lucas) [#1654](https://github.com/nodejs/io.js/pull/1654)
-->

* **win,node-gyp**: Windowsのアドオンの遅延読み込みのフックがデフォルトで適切に可能になりました。これは、リリースバージョン2.0.0では誤ってデフォルトがオフになっていました。 (Bert Belder) [#1433](https://github.com/nodejs/io.js/pull/1433)
* **os**: 現在のディレクトリが'/' にあるときに `tmpdir()` が行っていたスラッシュによる分割が issue を修正するために洗練されました。また、OSによって、どのスラッシュが使われるかということも考慮されました。(cjihrig) [#1673](https://github.com/nodejs/io.js/pull/1673)
* **tls**: デフォルトの暗号が gcm や aes128 を使うようにアップデートされました。(Mike MacCana) [#1660](https://github.com/nodejs/io.js/pull/1660)
* **build**: v8のスナップショットがv8のチームに提案されたように、再度デフォルトで可能になりました。以前のセキュリティの問題が解決されたからです。これでスタートアップする際とvmのコンテキストを作成する際の両方でパフォーマンスが改善するでしょう。(Trevor Norris) [#1663](https://github.com/nodejs/io.js/pull/1663)
* **src**: `--require` の前に他のフラグが使用された際に事前にロードしたモジュールが動かない問題が修正されました。(Yosuke Furukawa) [#1694](https://github.com/nodejs/io.js/pull/1694)
* **dgram**: `send()` のコールバックが非同期でなかったのが修正されました。(Yosuke Furukawa) [#1313](https://github.com/nodejs/io.js/pull/1313)
* **readline**: emitKeys はパースするのに十分になるまで、データをバッファするようになりました。これは、エスケープをパースする際のissueを解決しました。(Alex Kocharin) [#1601](https://github.com/nodejs/io.js/pull/1601)
* **cluster**: 適切に 'disconnect' を `cluster.worker` に送るようになりました。(Oleg Elifantiev) [#1386](https://github.com/nodejs/io.js/pull/1386)
* **events**: キャッチされないエラーはその状況を提供するようになりました。(Evan Lucas) [#1654](https://github.com/nodejs/io.js/pull/1654)

<!--
#### 2.1.0
-->

#### 2.1.0

<!--
* **crypto**: Diffie-Hellman key exchange (DHE) parameters (`'dhparams'`) must now be 1024 bits or longer or an error will be thrown. A warning will also be printed to the console if you supply less than 2048 bits. See https://weakdh.org/ for further context on this security concern (Shigeki Ohtsu) [#1739](https://github.com/nodejs/io.js/pull/1739).
* **node**: A new `--trace-sync-io` command line flag will print a warning and a stack trace whenever a synchronous API is used. This can be used to track down synchronous calls that may be slowing down an application (Trevor Norris) [#1707](https://github.com/nodejs/io.js/pull/1707).
* **node**: To allow for chaining of methods, the `setTimeout()`, `setKeepAlive()`, `setNoDelay()`, `ref()` and `unref()` methods used in `'net'`, `'dgram'`, `'http'`, `'https'` and `'tls'` now return the current instance instead of `undefined` (Roman Reiss & Evan Lucas) [#1699](https://github.com/nodejs/io.js/pull/1699) [#1768](https://github.com/nodejs/io.js/pull/1768) [#1779](https://github.com/nodejs/io.js/pull/1779).
* **npm**: Upgraded to v2.10.1, release notes can be found in <https://github.com/npm/npm/releases/tag/v2.10.1> and <https://github.com/npm/npm/releases/tag/v2.10.0>.
* **util**: A significant speed-up (in the order of 35%) for the common-case of a single string argument to `util.format()`, used by `console.log()` (Сковорода Никита Андреевич) [#1749](https://github.com/nodejs/io.js/pull/1749).
-->

* **crypto**: ディフィー・ヘルマン鍵共有(DHE)のパラメータ(`'dhparams'`)は1024ビット以上の長さでなければエラーがスローされるようになりました。また、2048ビットより短いとコンソールに警告がでます。このセキュリティの懸念についての詳細な状況については、 https://weakdh.org/ をご覧ください。(Shigeki Ohtsu) [#1739](https://github.com/nodejs/io.js/pull/1739).
* **node**: 新しいコマンドラインのフラグの `--trace-sync-io` は同期的なAPIが使用されるときにはいつでも警告とスタックトレースを出力します。これは、アプリケーションを遅くするであろう同期的な呼び出しを見つけるのに使われます。(Trevor Norris) [#1707](https://github.com/nodejs/io.js/pull/1707).
* **node**: メソッドを繋げることを許可するために、 `'net'` 、 `'dgram'` 、 `'http'` 、 `'https'` 、 `'tls'` で使われる `setTimeout()` 、 `setKeepAlive()` 、 `setNoDelay()` 、 `ref()` 、 `unref()` メソッドは`undefined` の代わりに現在のインスタンスをリターンするようになりました。(Roman Reiss & Evan Lucas) [#1699](https://github.com/nodejs/io.js/pull/1699) [#1768](https://github.com/nodejs/io.js/pull/1768) [#1779](https://github.com/nodejs/io.js/pull/1779).
* **npm**: v2.10.1にアップグレードされました。リリースノートは <https://github.com/npm/npm/releases/tag/v2.10.1> や <https://github.com/npm/npm/releases/tag/v2.10.0> で見ることができます。
* **util**: `console.log()` で使われる `util.format()` の単一の文字列引数の規格の重要な速度の向上（約35%）がありました。(Сковорода Никита Андреевич) [#1749](https://github.com/nodejs/io.js/pull/1749).

<!--
### Known issues
-->

### 既知の問題

<!--
See https://github.com/nodejs/io.js/labels/confirmed-bug for complete and current list of known issues.
-->

現在の完全な既知の問題リストはこちらを参照してください。 https://github.com/nodejs/io.js/labels/confirmed-bug

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
* Mikeal Rogers post about **Promise errors in io.js** on [Modulus.io](http://blog.modulus.io/promise-errors-in-iojs)
* [NodeSchool International Day](http://nodeschool.io/international-day/) has been held for the first time. [40 cities](https://github.com/nodeschool/international-day/issues?q=label%3Arollcall-2015+is%3Aclosed) joined.
* [Logjam](https://weakdh.org/) attack vulnerability detected on Diffie-Hellman Key exchange. io.js [fixed the vulnerability](https://github.com/nodejs/io.js/pull/1739) on [v2.1.0](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md#2015-05-24-version-210-rvagg).
-->

* Mikeal Rogers は**io.js における Promiseのエラー**についての投稿を[Modulus.io](http://blog.modulus.io/promise-errors-in-iojs)に行いました。
* [NodeSchool International Day](http://nodeschool.io/international-day/) が初めて行われました。[40の都市](https://github.com/nodeschool/international-day/issues?q=label%3Arollcall-2015+is%3Aclosed)が参加しました。
* [Logjam](https://weakdh.org/)攻撃の脆弱性がディフィー・ヘルマン鍵共有において見つかりました。io.jsは[v2.1.0](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md#2015-05-24-version-210-rvagg)で[脆弱性を修正](https://github.com/nodejs/io.js/pull/1739)しました。

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

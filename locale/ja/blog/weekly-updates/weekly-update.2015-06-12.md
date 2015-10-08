---
title: Weekly Update - Jun 12th, 2015
author: Giovanny Gioyik (@Gioyik)
date: 2015-06-12T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-06-12
layout: blog-post.hbs
---

<!--
# io.js 2.3 releases
-->

## io.js 2.3 リリース

<!--
This week we had one io.js release [v2.3.0](https://iojs.org/dist/v2.3.0/), complete changelog can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).
-->

今週は[v2.3.0](https://iojs.org/dist/v2.3.0/)をリリースしました。詳細は[GitHubにて](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md)確認いただけます。

<!--
### Notable changes
-->

### 主な変更点

<!--
* **libuv**: Upgraded to 1.6.0 and 1.6.1, see [full ChangeLog](https://github.com/libuv/libuv/blob/60e515d9e6f3d86c0eedad583805201f32ea3aed/ChangeLog#L1-L36) for details. (Saúl Ibarra Corretgé) [#1905](https://github.com/nodejs/io.js/pull/1905) [#1889](https://github.com/nodejs/io.js/pull/1889). Highlights include:
  - Fix TTY becoming blocked on OS X
  - Fix UDP send callbacks to not to be synchronous
  - Add `uv_os_homedir()` (exposed as `os.homedir()`, see below)
* **npm**: See full [release notes](https://github.com/npm/npm/releases/tag/v2.11.1) for details. (Kat Marchán) [#1899](https://github.com/nodejs/io.js/pull/1899). Highlight:
  - Use GIT_SSH_COMMAND (available as of Git 2.3)
* **openssl**:
  - Upgrade to 1.0.2b and 1.0.2c, introduces DHE man-in-the-middle protection (Logjam) and fixes malformed ECParameters causing infinite loop (CVE-2015-1788). See the [security advisory](https://www.openssl.org/news/secadv_20150611.txt) for full details. (Shigeki Ohtsu) [#1950](https://github.com/nodejs/io.js/pull/1950) [#1958](https://github.com/nodejs/io.js/pull/1958)
  - Support [FIPS](https://en.wikipedia.org/wiki/Federal_Information_Processing_Standards) mode of OpenSSL, see [README](https://github.com/nodejs/io.js#building-iojs-with-fips-compliant-openssl) for instructions. (Fedor Indutny) [#1890](https://github.com/nodejs/io.js/pull/1890)
* **os**: Add `os.homedir()` method. (Colin Ihrig) [#1791](https://github.com/nodejs/io.js/pull/1791)
* **smalloc**: Deprecate whole module. (Vladimir Kurchatkin) [#1822](https://github.com/nodejs/io.js/pull/1822)
* Add new collaborators:
  - Alex Kocharin ([@rlidwka](https://github.com/rlidwka))
  - Christopher Monsanto ([@monsanto](https://github.com/monsanto))
  - Ali Ijaz Sheikh ([@ofrobots](https://github.com/ofrobots))
  - Oleg Elifantiev ([@Olegas](https://github.com/Olegas))
  - Domenic Denicola ([@domenic](https://github.com/domenic))
  - Rich Trott ([@Trott](https://github.com/Trott))
-->

* **libuv**: 1.6.0と1.6.1へのアップデートを行いました。詳細は、こちらの[完全なチェンジログ](https://github.com/libuv/libuv/blob/60e515d9e6f3d86c0eedad583805201f32ea3aed/ChangeLog#L1-L36)をご覧ください。(Saúl Ibarra Corretgé) [#1905](https://github.com/nodejs/io.js/pull/1905) [#1889](https://github.com/nodejs/io.js/pull/1889)。詳細のハイライト:
  - OS XでTTYがブロックされる問題を修正
  - 同期せずに UDP send のコールバックを呼び出すように修正
  - `uv_os_homedir()` を追加 (`os.homedir()`として公開されているので、ドキュメントを参照してみてください)
* **npm**: 詳細は[リリースノート](https://github.com/npm/npm/releases/tag/v2.11.1)を参照してください。(Kat Marchán) [#1899](https://github.com/nodejs/io.js/pull/1899)。ハイライト:
  - GIT_SSH_COMMANDを使うようになりました(Git 2.3で使用可能に)
* **openssl**:
  - 1.0.2bと1.0.2cへのアップデートを行いました。(Logjamを悪用した)DHEの中間者攻撃からの保護と、無限ループを引き起こす不正な形式のECParametersの修正 (CVE-2015-1788) が含まれています。詳細は、[セキュリティ指南](https://www.openssl.org/news/secadv_20150611.txt)をご確認ください。(Shigeki Ohtsu) [#1950](https://github.com/nodejs/io.js/pull/1950) [#1958](https://github.com/nodejs/io.js/pull/1958)
  - OpenSSLの [FIPS](https://en.wikipedia.org/wiki/Federal_Information_Processing_Standards) モードをサポート。 使い方に関する詳細は、[README](https://github.com/nodejs/io.js#building-iojs-with-fips-compliant-openssl) をご確認ください。(Fedor Indutny) [#1890](https://github.com/nodejs/io.js/pull/1890)
* **os**: `os.homedir()` メソッドを追加。(Colin Ihrig) [#1791](https://github.com/nodejs/io.js/pull/1791)
* **smalloc**: モジュールの使用を非推奨としました。(Vladimir Kurchatkin) [#1822](https://github.com/nodejs/io.js/pull/1822)
* 新しいコラボレーターを受け入れ：
  - Alex Kocharin ([@rlidwka](https://github.com/rlidwka))
  - Christopher Monsanto ([@monsanto](https://github.com/monsanto))
  - Ali Ijaz Sheikh ([@ofrobots](https://github.com/ofrobots))
  - Oleg Elifantiev ([@Olegas](https://github.com/Olegas))
  - Domenic Denicola ([@domenic](https://github.com/domenic))
  - Rich Trott ([@Trott](https://github.com/Trott))

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
* Openssl vulnerabilities are updated on io.js. **Resume:** *Upgrade to 1.0.2b and 1.0.2c, introduces DHE man-in-the-middle protection (Logjam) and fixes malformed ECParameters causing infinite loop (CVE-2015-1788). See the security advisory for full details. (Shigeki Ohtsu) #1950 #1958*
* io.js 2.3.0 os.homedir() [ponyfill](http://t.co/2XQV5XQblu)
* ["Should I use Node.js or io.js? And which version?"](https://strongloop.com/strongblog/should-i-use-node-js-or-io-js-and-which-version/) article by StrongLoop
* iojs now supports [`--use_strong`](https://t.co/4t1EaiiK27). Strong mode (part of Google v8 experiments) implements a stronger semantics.
* ["Node.js and io.js Merge Under the Node Foundation"](http://www.infoq.com/news/2015/05/nodejs-iojs#.VX41fCR99Kc.twitter) by InfoQ.
-->

* io.jsに同梱されていたOpsnSSLの脆弱性は更新されました。
 **概要:** * 1.0.2bと1.0.2cへのアップデートでは、(Logjamを悪用した)DHEの中間者攻撃からの保護と、無限ループを引き起こす不正な形式のECParametersの修正 (CVE-2015-1788) が行われました。詳細なセキュリティについての情報は、(Shigeki Ohtsu) #1950 #1958 を確認してください。*
* io.js 2.3.0 の os.homedir() の [ponyfill](http://t.co/2XQV5XQblu) について。
* ["Node.js と io.js のどちらを使うべきか、そしてバージョンはいくつを使うべきか"](https://strongloop.com/strongblog/should-i-use-node-js-or-io-js-and-which-version/) by StrongLoop
* iojsは、[`--use_strong`](https://t.co/4t1EaiiK27) オプションをサポートしました。ストロングモード(Google V8の実験的機能)は、強いセマンティクスのチェックを行います。
* ["Node.js と io.js は、Node Foundationへとマージされる"](http://www.infoq.com/news/2015/05/nodejs-iojs#.VX41fCR99Kc.twitter) by InfoQ

<!--
### Upcoming Events
-->

## 今後開催されるイベント

<!--
* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State
* [BrazilJS Conf](http://braziljs.com.br/) tickets are on sale, August 21st - 22nd at Shopping Center BarraShoppingSul
* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
* [JSConf CO](http://www.jsconf.co/), October 16th - 17th at Ruta N, Medellin
-->

* [CascadiaJS](http://2015.cascadiajs.com/) のチケットが販売中です。7月8-10日にワシントン州にて開催されます。
* [BrazilJS Conf](http://braziljs.com.br/) のチケットが販売中です。8月21-22日にリオ・グランデ・ド・スール州のBarra Shopping Sulで開催されます。
* [NodeConf EU](http://nodeconf.eu/) のチケットが販売中です。9月6-9日にアイルランドのウォーターフォードにて開催されます。
* [JSConf CO](http://www.jsconf.co/)が10月16-17日にメデジンのル・タンにて開催されます。

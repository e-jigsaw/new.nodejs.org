---
title: Weekly Update - Jun 26th, 2015
author: Giovanny Gioyik (@Gioyik)
date: 2015-06-26T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-06-26
layout: blog-post.hbs
---

<!--
# io.js and Node.js News
This week we have one io.js [release v2.3.1](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md#2015-06-23-version-231-rvagg), complete changelog from previous releases can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).
-->

今週は[v2.3.1](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md#2015-06-23-version-231-rvagg)をリリースしました。詳細は[GitHubにて](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md)確認いただけます。

<!--
### Notable changes
-->

### 主な変更点

<!--
* **module**: The number of syscalls made during a `require()` have been significantly reduced again (see [#1801](https://github.com/nodejs/io.js/pull/1801) from v2.2.0 for previous work), which should lead to a performance improvement (Pierre Inglebert) [#1920](https://github.com/nodejs/io.js/pull/1920).
* **npm**:
  * Upgrade to [v2.11.2](https://github.com/npm/npm/releases/tag/v2.11.2) (Rebecca Turner) [#1956](https://github.com/nodejs/io.js/pull/1956).
  * Upgrade to [v2.11.3](https://github.com/npm/npm/releases/tag/v2.11.3) (Forrest L Norvell) [#2018](https://github.com/nodejs/io.js/pull/2018).
* **zlib**: A bug was discovered where the process would abort if the final part of a zlib decompression results in a buffer that would exceed the maximum length of `0x3fffffff` bytes (~1GiB). This was likely to only occur during buffered decompression (rather than streaming). This is now fixed and will instead result in a thrown `RangeError` (Michaël Zasso) [#1811](https://github.com/nodejs/io.js/pull/1811).
-->

* **module**: `require()` の際のいくつかの syscall を再び大幅に減少させました。(以前の v2.2.0 との違いは [#1801](https://github.com/nodejs/io.js/pull/1801) を参照してください) これはパフォーマンスの向上につながるはずです。 (Pierre Inglebert) [#1920](https://github.com/nodejs/io.js/pull/1920)
* **npm**:
  * [v2.11.2](https://github.com/npm/npm/releases/tag/v2.11.2) にアップグレードしました (Rebecca Turner) [#1956](https://github.com/nodejs/io.js/pull/1956)
  * [v2.11.3](https://github.com/npm/npm/releases/tag/v2.11.3) にアップグレードしました。 (Forrest L Norvell) [#2018](https://github.com/nodejs/io.js/pull/2018)
* **zlib**: バッファ内の zlib 解凍結果の最後の部分が `0x3fffffff` バイト(〜1GiB)の最大長を超えてしまい、その場合プロセスが中止されるバグが発見されました。これは、バッファ解凍時に発生する可能性がありました。この問題は修正され、代わりに `RangeError` が投げられます。(Michaël Zasso) [#1811](https://github.com/nodejs/io.js/pull/1811)

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
* Slide deck: [Bluemix Webinar: Deploying a Full Stack Node.js Application to IBM Bluemix](https://speakerdeck.com/bradleyholt/bluemix-webinar-deploying-a-full-stack-node-dot-js-application-to-ibm-bluemix)
* Article by RisingStack: [How to Use Rust with Node.js When Performance Matters](http://blog.risingstack.com/how-to-use-rust-with-node-when-performance-matters/)
* Device Atlas API now [supports Node.js](https://deviceatlas.com/blog/deviceatlas-api-node-js?utm_source=twitter&utm_medium=update&utm_campaign=node%20js%20support)
* [On Maintaining a Native Node Module](http://www.voodootikigod.com/on-maintaining-a-native-node-module/) by Chris Williams
* [nodei.co](http://twitter.com/rvagg/status/613688739030679552) is running with io.js
* npm [3.0.0 pre-release](https://github.com/npm/npm/releases/tag/v3.0.0)
-->

* スライド: [Bluemix Webinar: フルスタックの Node.js アプリケーションを IBM Bluemix にデプロイする](https://speakerdeck.com/bradleyholt/bluemix-webinar-deploying-a-full-stack-node-dot-js-application-to-ibm-bluemix)
* RisingStack の記事: [パフォーマンスのために Rust を Node.js と共に使う方法](http://blog.risingstack.com/how-to-use-rust-with-node-when-performance-matters/)
* Device Atlas API は[Node.js をサポート](https://deviceatlas.com/blog/deviceatlas-api-node-js?utm_source=twitter&utm_medium=update&utm_campaign=node%20js%20support)しました
* Chris Williams の記事: [ネイティブの Node Module をメンテナンスする](http://www.voodootikigod.com/on-maintaining-a-native-node-module/)
* [nodei.co](http://twitter.com/rvagg/status/613688739030679552) は io.js が動いています
* npm が [3.0.0](https://github.com/npm/npm/releases/tag/v3.0.0) をプレリリースしました

<!--
### Upcoming Events
-->

## 今後開催されるイベント

<!--
* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State
* [BrazilJS Conf](http://braziljs.com.br/) tickets are on sale, August 21st - 22nd at Shopping Center BarraShoppingSul
* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
* [Node.js Italian Conference](http://nodejsconf.it/) tickets are on sale, October 10th at Desenzano - Brescia, Italy
* [JSConf CO](http://www.jsconf.co/), October 16th - 17th at Ruta N, Medellin
-->

* [CascadiaJS](http://2015.cascadiajs.com/) のチケットが販売中です。7月8-10日にワシントン州にて開催されます。
* [BrazilJS Conf](http://braziljs.com.br/) のチケットが販売中です。8月21-22日にリオ・グランデ・ド・スール州のBarra Shopping Sulで開催されます。
* [NodeConf EU](http://nodeconf.eu/) のチケットが販売中です。9月6-9日にアイルランドのウォーターフォードにて開催されます。
* [Node.js Italian Conference](http://nodejsconf.it/) のチケットが販売中です。10月10日にイタリアのデゼンツァーノにて開催されます。
* [JSConf CO](http://www.jsconf.co/) が10月16-17日に、メデジンの Ruta N で開催されます。

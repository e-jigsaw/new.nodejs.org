---
title: Weekly Update - Jul 10th, 2015
author: Yosuke Furukawa (@yosuke-furukawa)
date: 2015-07-10T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-07-10
layout: blog-post.hbs
---

<!--
### io.js and Node.js News — July 10th
-->

# io.js/Node.js ウィークリーアップデート 2015/07/10

<!--
Security patches for io.js 1.8 and 2.3 and upcoming events.
-->

io.js 1.8 と 2.3 のセキュリティパッチ、イベント情報

<!--
### io.js 1.8 and 2.3 Releases
-->

## io.js 1.8 と 2.3 のリリース

<!--
This week we have two io.js releases: [v2.3.4](https://iojs.org/dist/v2.3.4/) and [v1.8.4](https://iojs.org/dist/v1.8.4/), complete changelog from previous releases can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md) with the [v1.x changelog here](https://github.com/nodejs/io.js/blob/v1.x/CHANGELOG.md).
-->

今週は io.js の [v2.3.4](https://iojs.org/dist/v2.3.4/) と [v1.8.4](https://iojs.org/dist/v1.8.4/) のリリースを行いました。詳細は [GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md) にて確認できます。v1.x のチェンジログは [こちら](https://github.com/nodejs/io.js/blob/v1.x/CHANGELOG.md)。

<!--
### Notable Changes
-->

### 主な変更点

<!--
#### 1.8.4
-->

#### 1.8.4

<!--
**Maintenance release**
-->

**メンテナンスリリース**

<!--
* **openssl**: Upgrade to 1.0.2d, fixes CVE-2015-1793 (Alternate Chains Certificate Forgery) [#2141](https://github.com/nodejs/io.js/pull/2141).
-->

* **openssl**: 1.0.2dにアップグレードしました。CVE-2015-1793 (Alternate Chains Certificate Forgery) を修正しました。 [#2141](https://github.com/nodejs/io.js/pull/2141)

<!--
#### 2.3.4
-->

#### 2.3.4

<!--
* **openssl**: Upgrade to 1.0.2d, fixes CVE-2015-1793 (Alternate Chains Certificate Forgery) (Shigeki Ohtsu) [#2141](https://github.com/nodejs/io.js/pull/2141).
* **npm**: Upgraded to v2.12.1, release notes can be found in <https://github.com/npm/npm/releases/tag/v2.12.0> and <https://github.com/npm/npm/releases/tag/v2.12.1> (Kat Marchán) [#2112](https://github.com/nodejs/io.js/pull/2112).
-->

* **openssl**: 1.0.2dにアップグレードしました。CVE-2015-1793 (Alternate Chains Certificate Forgery) (Shigeki Ohtsu) を修正しました。 [#2141](https://github.com/nodejs/io.js/pull/2141)
* **npm**: v2.12.1にアップグレードしました。詳細は  <https://github.com/npm/npm/releases/tag/v2.12.0> と <https://github.com/npm/npm/releases/tag/v2.12.1> を参照してください。(Kat Marchán) [#2112](https://github.com/nodejs/io.js/pull/2112)

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
* Surrogate pair in REPL can freeze terminal. [#690](https://github.com/nodejs/io.js/issues/690)
* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/nodejs/io.js/issues/760).
* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion. [#894](https://github.com/nodejs/io.js/issues/894)
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
* OpenSSL published a [high severity security issue](https://mta.openssl.org/pipermail/openssl-announce/2015-July/000037.html), io.js and Node.js have upgraded OpenSSL version and fixed the problem on latest version.
* Node.js LTS WG has updated [their proposed LTS plan](https://github.com/nodejs/LTS/blob/master/README.md#example). They need some feedbacks from Noders.
* ReactNative required io.js as [their test platform](https://github.com/facebook/react-native/blob/master/.travis.yml#L24).
-->

* OpenSSL は[重要度の高いセキュリティの問題](https://mta.openssl.org/pipermail/openssl-announce/2015-July/000037.html)について公開しました。io.js と Node.js は、最新バージョンでOpenSSLのバージョンを更新し、この問題を修正してあります。
* Node.js LTS WG は [彼らの提案する LTS plan](https://github.com/nodejs/LTS/blob/master/README.md#example) を更新しました。 Node使いの人のフィードバックをお待ちしています。
* ReactNative は [彼らのテスト環境 ](https://github.com/facebook/react-native/blob/master/.travis.yml#L24) に io.js を追加しました.

<!--
### Upcoming Events
-->

## 今後開催されるイベント

<!--
* [BrazilJS Conf](http://braziljs.com.br/) tickets are on sale, August 21st - 22nd at Shopping Center BarraShoppingSul
* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
* [Node.js Italian Conference](http://nodejsconf.it/) tickets are on sale, October 10th at Desenzano - Brescia, Italy
* [JSConf CO](http://www.jsconf.co/), October 16th - 17th at Ruta N, Medellin
-->

* [BrazilJS Conf](http://braziljs.com.br/) のチケットが販売中です。8月21-22日にリオ・グランデ・ド・スール州のBarra Shopping Sulで開催されます。
* [NodeConf EU](http://nodeconf.eu/) のチケットが販売中です。9月6-9日にアイルランドのウォーターフォードにて開催されます。
* [Node.js Italian Conference](http://nodejsconf.it/) のチケットが販売中です。10月10日にイタリアのデゼンツァーノにて開催されます。
* [JSConf CO](http://www.jsconf.co/) が10月16-17日に、メデジンの Ruta N で開催されます。

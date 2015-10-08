---
title: Weekly Update - Jul 3rd, 2015
author: Yosuke Furukawa (@yosuke-furukawa)
date: 2015-07-03T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-07-03
layout: blog-post.hbs
---

<!--
### io.js and Node.js News — July 3rd
Important patches for io.js 1.8 and 2.3 and upcoming events.
-->

# io.js ウィークリーアップデート 2015/07/03

io.js 1.8 と 2.3 の重要なパッチとイベント

<!--
### io.js 1.8 and 2.3 Releases
-->

## io.js 1.8 と 2.3 のリリース

<!--
This week we have three io.js releases: [v2.3.2](https://iojs.org/dist/v2.3.2/) and two following important security patches [v1.8.3](https://iojs.org/dist/v1.8.3/) and [v2.3.3](https://iojs.org/dist/v2.3.3/), complete changelog from previous releases can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md) with the [v1.x changelog here](https://github.com/nodejs/io.js/blob/v1.x/CHANGELOG.md).
-->

今週は、3つのリリースを行いました。[v2.3.2](https://iojs.org/dist/v2.3.2/)と、[v1.8.3](https://iojs.org/dist/v1.8.3/)と[v2.3.3](https://iojs.org/dist/v2.3.3/)の重要なセキュリティパッチです。完全なチェンジログは、[GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md)で確認できます。[v1.xのチェンジログはこちら](https://github.com/nodejs/io.js/blob/v1.x/CHANGELOG.md)。

<!--
### Notable Changes
-->

### 主な変更点

<!--
#### 1.8.3
-->

#### 1.8.3

<!--
**Maintenance release**
-->

**メンテナンスリリース**

<!--
* **v8**: Fixed an out-of-band write in utf8 decoder. **This is an important security update** as it can be used to cause a denial of service attack.
* **openssl**: Upgrade to 1.0.2b and 1.0.2c, introduces DHE man-in-the-middle protection (Logjam) and fixes malformed ECParameters causing infinite loop (CVE-2015-1788). See the [security advisory](https://www.openssl.org/news/secadv_20150611.txt) for full details. (Shigeki Ohtsu) [#1950](https://github.com/nodejs/io.js/pull/1950) [#1958](https://github.com/nodejs/io.js/pull/1958)
* **build**:
  * Added support for compiling with Microsoft Visual C++ 2015
  * Started building and distributing headers*only tarballs along with binaries
-->

* **v8**: UTF8デコーダのアウトオブバンドの記述を修正しました。 **これは重要なセキュリティのアップデートです。** DoS攻撃を引き起こす可能性があったためです。
* **openssl**: 1.0.2b そして 1.0.2c にアップグレードしました。DHE中間者攻撃（Logjam）に対する防御を導入し、無限ループを引き起こすmalformed ECParameters(CVE-2015-1788)を修正しました。詳細については[セキュリティ勧告](https://www.openssl.org/news/secadv_20150611.txt)をご覧ください。 (Shigeki Ohtsu) [#1950](https://github.com/nodejs/io.js/pull/1950) [#1958](https://github.com/nodejs/io.js/pull/1958)
* **build**:
  * Microsoft Visual C++ 2015でのコンパイルのサポートを開始しました。
  * バイナリと共にヘッダーのみのターボールのビルドと配布を開始しました。

<!--
#### 2.3.2
-->

#### 2.3.2

<!--
* **build**:
  * Added support for compiling with Microsoft Visual C++ 2015
  * Started building and distributing headers-only tarballs along with binaries
-->

* **build**:
  * Microsoft Visual C++ 2015でのコンパイルのサポートを開始しました。
  * バイナリと共にヘッダーのみのターボールのビルドと配布を開始しました。

<!--
#### 2.3.3
-->

<!--
* **deps**: Fixed an out-of-band write in utf8 decoder. **This is an important security update** as it can be used to cause a denial of service attack.
-->

* **deps**: UTF8デコーダのアウトオブバンドの記述を修正しました。 **これは重要なセキュリティのアップデートです。** DoS攻撃を引き起こす可能性があったためです。

<!--
### Known Issues
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
* Yosuke Furukawa will give a talk about the past, present, and future of Node.js in [YAPC Asia 2015](http://yapcasia.org/2015/), the largest conference in Japan's programming community. It will be hosted at Tokyo on August 20th - 22nd and his talk will specifically be on the 22nd. Details of the talk can be found [here](http://yapcasia.org/2015/talk/show/82e93a96-f60e-11e4-907e-8ab37d574c3a).
* A security issue is found in v8 that can be used for DoS attacks against Node.js applications and servers running 0.12 and all versions of io.js. Critical security upgrades ([Node.js v0.12.6](http://nodejs.org/dist/v0.12.6/), [io.js 2.3.3](https://iojs.org/dist/v2.3.3/) and [io.js 1.8.3](https://iojs.org/dist/v1.8.3/)) have been released. Also, details about the issue can be found [on one of our Medium post](https://medium.com/@iojs/important-security-upgrades-for-node-js-and-io-js-8ac14ece5852). If you're running v1.8.2 or below, or v2.3.2 or below, please update them to io.js versions 1.8.3 and 2.3.3.
-->

* Yosuke Furukawa は日本のプログラミングのコミュニティの中で1番大きい[YAPC Asia 2015](http://yapcasia.org/2015/)というイベントで、Node.jsの過去、現在、未来について話します。このイベントは東京で8月20日から22日まで開かれます。彼のトークは22日に行われます。トークの詳細については、[こちら](http://yapcasia.org/2015/talk/show/82e93a96-f60e-11e4-907e-8ab37d574c3a)をご覧ください。
* セキュリティの問題がv8に見つかり、Node.js 0.12とio.jsの全てのバージョンのアプリケーションやサーバに対して、DoS攻撃に利用される可能性があります。重要なセキュリティのアップグレード([Node.js v0.12.6](http://nodejs.org/dist/v0.12.6/)、 [io.js 2.3.3](https://iojs.org/dist/v2.3.3/) と [io.js 1.8.3](https://iojs.org/dist/v1.8.3/))がリリースされました。また、問題の詳細は[ブログの記事](http://blog.iojs.jp/important_security_issue.html)で読むことができます。もしio.jsをv1.8.2以下か、v2.3.2以下で運用している場合は、1.8.3か2.3.3にアップデートを行ってください。

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

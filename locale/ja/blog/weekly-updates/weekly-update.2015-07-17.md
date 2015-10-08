---
title: Weekly Update - Jul 17th, 2015
author: Yosuke Furukawa (@yosuke-furukawa)
date: 2015-07-17T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-07-17
layout: blog-post.hbs
---

<!--
### io.js and Node.js News — July 17th
-->

# io.js / Node.js ウィークリーアップデート 2015/07/17

<!--
io.js 2.4.0 is released, Apigee joined our foundation and Intl WG start.
-->

io.js 2.4.0 のリリース、ApigeeがFoundationに参加、Intl WG が開始

<!--
### io.js 2.4 Release
-->

## io.js 2.4 リリース

<!--
This week we have one io.js release: [v2.4.0](https://iojs.org/dist/v2.4.0/), complete changelog from previous releases can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).
-->

今週は、io.js [v2.4.0](https://iojs.org/dist/v2.4.0/) をリリースしました。詳細は [GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md) にて確認できます。

<!--
### Notable Changes
-->

### 主な変更点

<!--
#### 2.4.0
-->

#### 2.4.0

<!--
* **src**: Added a new `--track-heap-objects` flag to track heap object allocations for heap snapshots (Bradley Meck) [#2135](https://github.com/nodejs/io.js/pull/2135).
* **readline**: Fixed a freeze that affected the repl if the keypress event handler threw (Alex Kocharin) [#2107](https://github.com/nodejs/io.js/pull/2107).
* **npm**: Upgraded to v2.13.0, release notes can be found in <https://github.com/npm/npm/releases/tag/v2.13.0> (Forrest L Norvell) [#2152](https://github.com/nodejs/io.js/pull/2152).
-->

* **src**: 新たに `--track-heap-objects` フラグを追加しました。ヒープのスナップショットのためのヒープオブジェクトをトラックします。 (Bradley Meck) [#2135](https://github.com/nodejs/io.js/pull/2135)
* **readline**: キープレスイベントハンドラーが例外を投げた影響でreplがfreezeするのを修正しました。 (Alex Kocharin) [#2107](https://github.com/nodejs/io.js/pull/2107)
* **npm**: v2.13.0に更新しました。詳細は <https://github.com/npm/npm/releases/tag/v2.13.0> を参考にしてください。 (Forrest L Norvell) [#2152](https://github.com/nodejs/io.js/pull/2152)

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
* NodeSource announces N|Support on [their blog post](https://nodesource.com/blog/nodesource-announces-nsupport). N|Support is a premium support offering for Node.js developers, DevOps and IT operations teams. To learn more about N|Support offerings, check out [the solution page](https://nodesource.com/products/nsupport).
* [Apigee](https://apigee.com/) is [added to the Node Foundation](https://github.com/nodejs/nodejs.org/pull/151)
* [joyent/docker-node](https://github.com/joyent/docker-node) team is moved to [nodejs/docker](https://github.com/nodejs/docker-iojs) team. As a result, [@chorrell](https://github.com/chorrell) and [@dcrudgington](https://github.com/dcrudgington) joined [@nodejs/docker](https://github.com/orgs/nodejs/teams/docker) team.
* [Intl](https://github.com/nodejs/intl) WG is launched. They are dedicated to support and improvement of Internationalization and Localization in Node. Intl WG calls for participants in [their issue](https://github.com/nodejs/Intl/issues/5).
-->

* NodeSource は N|Support を [彼らのブログ記事 ](https://nodesource.com/blog/nodesource-announces-nsupport) にて発表しました。 N|Support は、Node.js 開発者、DevOps、IT運用チームを支援するプレミアムサポートです。N|Support についての詳細を知りたい方は、[the solution page](https://nodesource.com/products/nsupport) を参照してください。
* [Apigee](https://apigee.com/) は [Node Foundation に参加](https://github.com/nodejs/nodejs.org/pull/151) しました。
* [joyent/docker-node](https://github.com/joyent/docker-node) チームは [nodejs/docker](https://github.com/nodejs/docker-iojs) チームへと移動しました。結果的に、[@chorrell](https://github.com/chorrell) と [@dcrudgington](https://github.com/dcrudgington) は [@nodejs/docker](https://github.com/orgs/nodejs/teams/docker) チームに参加となりました。
* [Intl](https://github.com/nodejs/intl) WG が開始されました。このWGは、Nodeのサポート・国際化・ローカリゼーションを行います。 Intl WG は、参加者を [issueのページ](https://github.com/nodejs/Intl/issues/5) で募集しています。

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

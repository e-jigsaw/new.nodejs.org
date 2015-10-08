---
title: Weekly Update - Mar 13th, 2015
author: Julian Duque (julianduque) & Yosuke Furukawa (yosuke-furukawa)
date: 2015-03-13T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-03-13
layout: blog-post.hbs
---

<!--
# io.js 1.5.1 Release
-->

## io.js 1.5.1 リリース

<!--
On Monday, March 9th, [@rvagg](https://github.com/rvagg) released io.js [v1.5.1](https://iojs.org/dist/v1.5.1/). The complete change log can be found [on GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).
-->

3月9日(月)に [@rvagg](https://github.com/rvagg) は io.js [v1.5.1](https://iojs.org/dist/v1.5.1/) をリリースしました。完全なチェンジログは [GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md) で確認することができます。

<!--
### Notable changes
-->

### 主な変更点

<!--
* **tls**: The reported TLS memory leak has been resolved via various commits in this release. Current testing indicated that there _may_ still be some leak problems. Track complete progress at [#1075](https://github.com/iojs/io.js/issues/1075).
* **http**: Fixed an error reported at [joyent/node#9348](https://github.com/joyent/node/issues/9348) and [npm/npm#7349](https://github.com/npm/npm/issues/7349). Pending data was not being fully read upon an `'error'` event leading to an assertion failure on `socket.destroy()`. (Fedor Indutny) [#1103](https://github.com/iojs/io.js/pull/1103)
-->

* **tls**: 報告されていた TLS のメモリリークについてこのリリースのさまざまなコミットによって解決されました。現在のテストにおいてまだいくつかの __メモリリークが存在し得ること__ が示されています。全ての詳細な進捗は [#1075](https://github.com/iojs/io.js/issues/1075) で追ってください。
* **http**: [joyent/node#9348](https://github.com/joyent/node/issues/9348) と [npm/npm#7349](https://github.com/npm/npm/issues/7349) で報告されたエラーを修復しました。`socket.destroy()` に失敗したときの `'error'` イベントに続く未解決のデータが完全に読まれていませんでした。(Fedor Indutny) [#1103](https://github.com/iojs/io.js/pull/1103)

<!--
### Known issues
-->

### 既知の問題

<!--
* Possible remaining TLS-related memory leak(s), details at [#1075](https://github.com/iojs/io.js/issues/1075).
* Windows still reports some minor test failures and we are continuing to address all of these as a priority. See [#1005](https://github.com/iojs/io.js/issues/1005).
* Surrogate pair in REPL can freeze terminal [#690](https://github.com/iojs/io.js/issues/690)
* Not possible to build io.js as a static library [#686](https://github.com/iojs/io.js/issues/686)
* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/iojs/io.js/issues/760) and fix in [#774](https://github.com/iojs/io.js/issues/774)
* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion [#894](https://github.com/iojs/io.js/issues/894)
-->

* TLS 関連のメモリリークが依然として発生することがあります。詳細は [#1075](https://github.com/iojs/io.js/issues/1075) にて。
* Windows はまだいくつかのマイナーなテストの失敗が報告されており、我々は優先的にこれら全ての対処を続けています。詳細は [#1005](https://github.com/iojs/io.js/issues/1005)。
* REPL 内のサロゲートペアがターミナルをフリーズさせることが可能です。[#690](https://github.com/iojs/io.js/issues/690)
* 静的ライブラリとして io.js をビルドすることができません。[#686](https://github.com/iojs/io.js/issues/686)
* child_process から生成された際の `process.send()` は[ドキュメントに記述されている](https://iojs.org/api/child_process.html#child_process_child_send_message_sendhandle)通り、本来は同期的に実行されるはずですが、1.0.2 によって発生した不具合により非同期的に呼び出されてしまうようになりました。詳細は [#760](https://github.com/iojs/io.js/issues/760) そして issue [#774](https://github.com/iojs/io.js/issues/774) で修正中です。
* `dns.setServers()` を呼び出す間の DNS クエリが進行中にアサーションに失敗してプロセスをクラッシュさせることがあります。[#894](https://github.com/iojs/io.js/issues/894)

<!--
# Community Updates
-->

## コミュニティアップデート

<!--
* [Tony Pujals] (https://twitter.com/subfuzion) gave the io.js roadmap presentation to [BayNode](http://www.meetup.com/BayNode/events/220246228/). The video was posted to [vimeo](https://vimeo.com/121707989) on March 9. Slides are available for anyone to give at their [local meetup](ron.buell@rd.io).
* [Johan Bergström](https://github.com/jbergstroem) is working on getting a patch into [V8](https://codereview.chromium.org/990063002) on behalf of io.js to bring Solaris support back into the latest version
* [NodeUp Episode 84](http://nodeup.com/eightyfour) it's io.js update #1 with [Mikeal Rogers](https://github.com/mikeal), [Trevor Norris](https://github.com/trevnorris) and [Bradley Meck](https://github.com/bmeck)
* [Mikeal Rogers](https://github.com/mikeal) was interviewed for [Descriptive](http://descriptive.audio) podcast on an episoded called [We've Never Had This Many Active Contributors to Core Before](http://descriptive.audio/episodes/12)
* [Mark Wolfe](https://twitter.com/wolfeidau) gave a [talk about io.js](https://twitter.com/wolfeidau/status/575785856545378304) at [@melbjs](https://twitter.com/melbjs) meetup, slides are published [here](https://speakerdeck.com/wolfeidau/iojs-bringing-es6-to-the-node)
* [dockeri.co](http://dockeri.co/) now runs on io.js, you can see the announcement [here](https://twitter.com/wjblankenship/status/575867637680369665)
* [Node.js Advisory Board](https://nodejs.org/about/advisory-board/) are talking about the [io.js/Node.js reconciliation proposal](https://github.com/iojs/io.js/issues/978), you can check the meeting minutes [here](https://github.com/joyent/nodejs-advisory-board/blob/master/meetings/2015-03-09/minutes.md#nodejsiojs-reconciliation-bb)
-->

* [Tony Pujals](https://twitter.com/subfuzion) は [BayNode](http://www.meetup.com/BayNode/events/220246228/) にて io.js ロードマップのプレゼンテーションをしました。ビデオは3月9日に [vimeo](https://vimeo.com/121707989) に投稿されました。スライドは[ローカルミートアップ](ron.buell@rd.io)で誰でも使うことができます。
* [Johan Bergström](https://github.com/jbergstroem) は [V8](https://codereview.chromium.org/990063002) のパッチを作成中で、これは io.js 最新版の Solaris サポートをもたらすでしょう。
* [NodeUp Episode 84](http://nodeup.com/eightyfour) に [Mikeal Rogers](https://github.com/mikeal), [Trevor Norris](https://github.com/trevnorris) と [Bradley Meck](https://github.com/bmeck) が出演し、io.js について語っています。
* [Mikeal Rogers](https://github.com/mikeal) は [Descriptive](http://descriptive.audio) のインタビューを受け、[我々は今までで最もアクティブなコアコントリビュータがいます](http://descriptive.audio/episodes/12)というタイトルで公開されています。
* [Mark Wolfe](https://twitter.com/wolfeidau) は [@melbjs](https://twitter.com/melbjs) で [io.js について発表し](https://twitter.com/wolfeidau/status/575785856545378304)、スライドは[こちら](https://speakerdeck.com/wolfeidau/iojs-bringing-es6-to-the-node)で公開されています。
* [dockeri.co](http://dockeri.co/) で io.js を実行することができるようになりました。アナウンスは[こちら](https://twitter.com/wjblankenship/status/575867637680369665)です。
* [Node.js Advisory Board](https://nodejs.org/about/advisory-board/) は [io.js/Node.js の和解プロポーザル](http://blog.iojs.jp/reconciliation_proposal.html)について話しました。議事録は[こちら](https://github.com/joyent/nodejs-advisory-board/blob/master/meetings/2015-03-09/minutes.md#nodejsiojs-reconciliation-bb)で読むことができます。

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

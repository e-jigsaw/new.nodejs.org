---
title: Weekly Update - Mar 27th, 2015
author: Yosuke Furukawa (yosuke-furukawa)
date: 2015-03-27T12:00:00.000Z
status: publish
category: weekly
slug: weekly-update-2015-03-27
layout: blog-post.hbs
---

<!--
# io.js 1.6.2 release
-->

## io.js 1.6.2 リリース

<!--
This week we had one io.js releases [v1.6.2](https://iojs.org/dist/v1.6.2/), complete changelog can be found [on GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).
-->

私たちは io.js の [v1.6.2](https://iojs.org/dist/v1.6.2/) を今週リリースしました。完全なチェンジログは [GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md) で確認できます。

<!--
### Notable changes
-->

### 主な変更点

#### 1.6.2

<!--
* **Windows**: The ongoing work in improving the state of Windows support has resulted in full test suite passes once again. As noted in the release notes for v1.4.2, CI system and configuration problems prevented it from properly reporting problems with the Windows tests, the problems with the CI and the codebase appear to have been fully resolved.
* **FreeBSD**: A [kernel bug](https://lists.freebsd.org/pipermail/freebsd-current/2015-March/055043.html) impacting io.js/Node.js was [discovered](https://github.com/joyent/node/issues/9326) and a patch has been introduced to prevent it causing problems for io.js (Fedor Indutny) [#1218](https://github.com/iojs/io.js/pull/1218).
* **module**: you can now `require('.')` instead of having to `require('./')`, this is considered a bugfix (Michaël Zasso) [#1185](https://github.com/iojs/io.js/pull/1185).
* **v8**: updated to 4.1.0.25 including patches for `--max_old_space_size` values above `4096` and Solaris support, both of which are already included in io.js.
-->

* **Windows**: Windows のサポート状態を改善するために作業しており、再び全てのテストスイートをパスしました。`v1.4.2` のリリースノートに書かれていますが、Windows のテストでは CI システムと設定の問題で適切に問題が報告されていませんでした。しかし、これらの問題は全て解決されています。
* **FreeBSD**: カーネルの[バグ](https://lists.freebsd.org/pipermail/freebsd-current/2015-March/055043.html)は io.js/Node.js に衝撃をもたらしましたが、原因は[発見](https://github.com/joyent/node/issues/9326)され、パッチがあてられました。(Fedor Indutny) [#1218](https://github.com/iojs/io.js/pull/1218)
* **module**: `require('.')` を `require('./')` の代わりに使用することができます。これはバグ修正です。(Michaël Zasso) [#1185](https://github.com/iojs/io.js/pull/1185)
* **v8**: バージョンを `4.1.0.25` にアップデートし、`--max_old_space_size` において `4096` のような値や、Solaris のサポートなどが含まれています。これらは既に io.js に組み込まれています。

<!--
### Known issues
-->

### 既知の問題

<!--
* Possible small memory leak(s) may still exist but have yet to be properly identified, details at [#1075](https://github.com/iojs/io.js/issues/1075).
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
* Node.js Technical Governance Draft is proposed, you can check the draft [here](https://github.com/joyent/nodejs-advisory-board/pull/30)
* Microsoft Visual Studio team releases Node.js Tools 1.0 for Visual Studio, the release includes rich editor, code completions, interactive window, advanced debugging and profiling. Check [the announcement](http://blogs.msdn.com/b/visualstudio/archive/2015/03/25/node-js-tools-1-0-for-visual-studio.aspx).
* [SPM monitor supports node.js and io.js](http://blog.sematext.com/2015/03/30/nodejs-iojs-monitoring/), the monitor adds performance monitoring, alerting, and anomaly detection.
-->

* Node.js Technical Governance のドラフトが提案されました。[こちら](https://github.com/joyent/nodejs-advisory-board/pull/30)より確認することができます(英語)。
* Microsoft の Visual Studio のチームは Node.js Tools 1.0 for Visual Studio をリリースしました。このリリースには、高級なエディタ、コード補完、インタラクティブウィンドウ、強力なデバッグ、分析などが含まれています。詳しくは[アナウンス](http://blogs.msdn.com/b/visualstudio/archive/2015/03/25/node-js-tools-1-0-for-visual-studio.aspx)を確認ください。
* [SPM monitor は node.js と io.js をサポートしました](http://blog.sematext.com/2015/03/30/nodejs-iojs-monitoring/)。パフォーマンスのモニタリング、アラート、異常値の検出が可能になります。

<!--
# Upcoming Events
-->

## 今後開催されるイベント

<!--
* [NodeConf](http://nodeconf.com/) tickets are on sale, June 8th and 9th at Oakland, CA and NodeConf Adventure for June 11th - 14th at Walker Creek Ranch, CA
* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State
* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
* [nodeSchool tokyo](http://nodejs.connpass.com/event/13182/) will be held in April 12th at Tokyo, Japan
-->

* [NodeConf](http://nodeconf.com/) のチケットが販売中です。6月8-9日にカルフォルニアのオークランドにて開催され、11-14日は NodeConf Adventure がウォーカークリークランチにて開催されます。
* [CascadiaJS](http://2015.cascadiajs.com/) のチケットも販売中です。7月8-10日にワシントン州にて開催されます。
* [NodeConf EU](http://nodeconf.eu/) のチケットも販売中です。9月6-9日にアイルランドのウォーターフォードにて開催されます。
* [NodeSchool Tokyo](http://nodejs.connpass.com/event/13182/) が4月12日に東京で開催されます。

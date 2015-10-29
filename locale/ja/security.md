---
layout: security.hbs
title: Security
---
<!--
# Security
-->

# セキュリティ

<!--
## Reporting a Bug
-->

## バグの報告について

<!--
All security bugs in Node.js are taken seriously and should be reported by emailing [security@nodejs.org](mailto:security@nodejs.org).
This will be delivered to a subset of the core team who handle security issues.
-->

Node.js の全てのセキュリティバグはメールで報告する必要があります。メールアドレスは[security@nodejs.org](mailto:security@nodejs.org)です。
これはセキュリティ上の問題を処理するコアチームの一部に配信されます。

<!--
Your email will be acknowledged within 24 hours, and you’ll receive a more detailed response to your email within 48
hours indicating the next steps in handling your report.
-->

あなたのメールは24時間以内に確認され、48時間以内にレポートを処理する際の次のステップを示すより詳細なメールを受け取るでしょう。

<!--
After the initial reply to your report, the security team will endeavor to keep you informed of the progress being made
towards a fix and full announcement, and may ask for additional information or guidance surrounding the reported issue.
These updates will be sent at least every five days, in practice, this is more likely to be every 24-48 hours.
-->

最初に返信した後、修正とアナウンスを行うために、セキュリティチームから追加の情報や手順を尋ねることがあります。これらのアップデートは遅くとも5日以内に、実際には24-48時間以内に送信されるでしょう。

<!--
Security bugs in third party modules should be reported to their respective maintainers and can also be coordinated
through the [Node Security Project](https://nodesecurity.io).
-->

サードパーティ製のモジュールでのセキュリティバグはそれぞれのメンテナに報告するか、[Node セキュリティプロジェクト](https://nodesecurity.io)で報告することもできます。

<!--
Thank you for improving the security of Node.js. Your efforts and responsible disclosure are greatly appreciated and
will be acknowledged.
-->

Node.js のセキュリティ向上に協力いただきありがとうございます。あなたの努力と責任ある開示は高く評価され知られることとなるでしょう。

<!--
## Disclosure Policy
-->

## ディスクロージャポリシー

<!--
Here is the security disclosure policy for Node.js
-->

Node.js のディスクロージャポリシーは以下になります。

<!--
- The security report is received and is assigned a primary handler. This person will coordinate the fix and release
process. The problem is confirmed and a list of all affected versions is determined. Code is audited to find any
potential similar problems. Fixes are prepared for all releases which are still under maintenance. These fixes are not
committed to the public repository but rather held locally pending the announcement.
-->

- セキュリティレポートは受信されると第1のハンドラが割り当てられます。この人は修正とリリースのプロセスを調整します。問題は確認され、影響のあるバージョンが決定されます。コードは潜在的な同様の問題のために監査されます。修正は全てのリリースに対して準備されます。これらの修正は発表がされるまで公開リポジトリにはコミットされず、ローカルに保持されます。

<!--
- A suggested embargo date for this vulnerability is chosen and a CVE (Common Vulnerabilities and  Exposures (CVE®))
is requested for the vulnerability.
-->

- この脆弱性に対して公表する日が提案され、CVE(共通脆弱性(CVE®))が脆弱性のために要求されます。

<!--
- On the embargo date, the Node.js security mailing list is sent a copy of the announcement. The changes are pushed to
the public repository and new builds are deployed to nodejs.org. Within 6 hours of the mailing list being notified, a
copy of the advisory will be published on the Node.js blog.
-->

- 公表の日には Node.js セキュリティメーリングリストにアナウンスのコピーが送られます。変更は公開リポジトリにプッシュされ、新しいビルドが nodejs.org にデプロイされます。6時間以内にメーリングリストに通知され、アドバイザリのコピーが Node.js ブログに公開されます。

<!--
- Typically the embargo date will be set 72 hours from the time the CVE is issued. However, this may vary depending on
the severity of the bug or difficulty in applying a fix.
-->

- 一般的には CVE の公表日は発表されてから72時間以内に決定されます。ただし、これは修正の難度や重症度に応じて異なる場合があります。

<!--
- This process can take some time, especially when coordination is required with maintainers of other projects. Every
effort will be made to handle the bug in as timely a manner as possible, however, it’s important that we follow the
release process above to ensure that the disclosure is handled in a consistent manner.
-->

- このプロセスには時間がかかることがあり、特に他のプロジェクトでメンテナが必要とされている場合です。即時にバグを修正するために努力しますが、我々が一貫性をもって処理していることを保証し開示するために上記のプロセスに従うことが重要です。

<!--
## Receiving Security Updates
-->

## セキュリティアップデートを受け取る

<!--
Security notifications will be distributed via the following methods.
-->

セキュリティの通知を受け取るには以下の方法があります。

- [http://groups.google.com/group/nodejs-sec](http://groups.google.com/group/nodejs-sec)
- [http://blog.nodejs.org](http://blog.nodejs.org)

<!--
## Comments on this Policy
-->

## ポリシーに対するコメント

<!--
If you have suggestions on how this process could be improved please submit a [pull request](https://github.com/joyent/node-website)
or email [security@nodejs.org](mailto:security@nodejs.org) to discuss.
-->

もしこのプロセスをよりよくする提案があれば [pull request](https://github.com/nodejs/new.nodejs.org) を送るか [security@nodejs.org](mailto:security@nodejs.org) までメールいただき議論しましょう。

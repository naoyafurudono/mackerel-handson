---
title: おまけ
lang: ja-jp
---

# おまけ

## 障害を自動復旧させる

[『公式チェックプラグインを導入する』](/06_check_plugins/)のハンズオンで設定したチェック監視では、監視を行った結果に応じて任意のコマンドを実行する`action`オプションが用意されています。

ハンズオンではhttpdプロセスの監視を実践したので、httpdプロセスのダウンを検知したらhttpdプロセスの自動復旧を行うように`action`を定義してみましょう。

先ほどの設定に`action = ...`の行を追加してください。

```toml
action = { command = "bash -c '[ \"$MACKEREL_STATUS\" != \"OK\" ]' && systemctl start httpd" }
```

以下のように設定ができれば完了です。

```toml
[plugin.checks.proc_httpd]
command = ["check-procs", "--pattern", "httpd"]
action = { command = "bash -c '[ \"$MACKEREL_STATUS\" != \"OK\" ]' && systemctl start httpd" }
```

`action`オプションを指定すると監視が行われる度に`action`に指定された`command`が実行されます。
その際、監視の実行結果が環境変数`$MACKEREL_STATUS`に代入されるので、`OK`以外だった場合にhttpdを起動するコマンドを実行して自動復旧させるといった仕組みになります。

それでは、mackerel-agentの再起動とhttpdプロセスを停止してアラートの発報から自動復旧がされるか確認してみましょう。

```shell
sudo systemctl restart mackerel-agent
sudo systemctl stop httpd
```

アラートが発報されたらホスト上でhttpdのプロセスが復旧していることを確認します。

```shell
ps aux | grep httpd
```

無事に復旧されているでしょうか！？


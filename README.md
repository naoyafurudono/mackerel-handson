# Mackerel Hands-On

※こちらは、[Mackerel Hands-On Seminar](http://mackerelio.connpass.com/event/38331/)で用いる手順ページです。<br>
<br>
Mackerel Hands-On Seminar へようこそ。<br>
このハンズオンでは、mackerel-agentのインストールからブラウザ上でのグラフの確認、プラグインの便利な使い方などをガイドしていきます。<br>
ワクワクする時間になれば幸いです。<br>

# 事前準備

- PC
 - Windows または Mac
 - ターミナルソフトを利用しますので、事前にインストールや設定などをお願いします
- 外部への SSH 接続が可能なネットワーク環境
- この場で受信可能なメールアドレス
 - セミナー中に発生させるアラートの通知先としても利用します

# Mackerel Hands-On Seminar 入力コマンド一覧
## <a name="2">2. 監視対象サーバーと Mackerel の準備</a>
### 【手順１】ログインコマンドの確認

Mackerel Hands-On Seminar では、ハンズオンで用いるサーバーをあらかじめご用意しています。

ログインコマンドは別 URL にて公開しています。ログインができることを確認してみてください。


### 【手順２】ホスト名（サーバー名）の変更
ログインすることができたら、まずは肩慣らしとして、ホスト名の変更を行ってみましょう。

<div class="clip">
  <pre><code class="target">sudo hostname 【お名前など】-host</code></pre>
  <button type="button" class="clip-button">Copy</button>
</div>

例えば `sudo hostname suzuki-host` などです。ホスト名にはアンダーバー `_` を使うことができませんのでご注意下さい。

コマンドを実行しようとすると、パスワードを聞かれますので、ログインのときに入力したものと同じパスワードを入力してください。

特にエラーなどが出ず、再びコマンドが入力できる状態になったら成功です。


### 【手順３】ホスト名（サーバー名）の変更を確認

<div class="clip">
  <pre><code class="target">hostname</code></pre>
  <button type="button" class="clip-button">Copy</button>
</div>

`suzuki-host` など、手順２で決めたホスト名が表示されたら OK です。


### 【手順４】Mackerel のアカウントを作成（サインアップ）

[https://mackerel.io/signup](https://mackerel.io/signup) から、アカウントの作成（サインアップ）を行ってください。

今日この場で受信可能なメールアドレスでの登録をお願いします。

すでにアカウントを持っている方は、講師の指示のもと、新規オーガニゼーションを作成してください。


## <a name="3">3. エージェントのインストール・起動・GUI の確認</a>
ここで行って頂くことは、下記3つの手順です。

* エージェント（mackerel-agent）のインストール
* エージェント（mackerel-agent）の設定
* エージェント（mackerel-agent）の起動

これらの手順は、[オーガニゼーションの作成完了後に表示されている画面](https://mackerel.io/my/instruction)の「2. 新規ホストを登録する」に従って作業を進めてみてください。

### 【手順５】グラフを確認する

エージェントが起動すると、サーバの構成情報や動作状況がMackerelのサーバに送信されるようになります。
早速グラフを確認してみましょう。[グラフを確認する](https://mackerel.io/my/hosts)


## <a name="4">4. 監視の設定・アラートの確認</a>
### 【手順６】CPU に負荷を掛けてみる

監視対象サーバにログインしたあとに、以下のコマンドを実行し意図的に CPU に負荷を掛けてみます。

<div class="clip">
  <pre><code class="target">yes > /dev/null</code></pre>
  <button type="button" class="clip-button">Copy</button>
</div>

`y` を延々と出力するコマンド `yes` を実行します。（その出力をただ捨てるだけのコマンドです。）

実行できたら、Mackerel のホスト詳細画面を表示させてみましょう。

### 【手順７】アラートタブを確認してみる

あらかじめ設定しておいた監視ルールに抵触すると、アラートタブ画面に何らかの変化が起こるはずです。
確認してみましょう。[アラートタブ画面](https://mackerel.io/my/alerts)


### 【手順８】CPUに負荷を掛けるコマンドの停止

CPU に負荷をかけるコマンドがまだ実行中だと思います。

実行中の画面を開き、そのまま【Ctrl キーと `C` キー】を押して下さい。

コマンドの実行がキャンセルされます。

キャンセルできたら、また CPU のグラフの変化をリアルタイムで見守ってみましょう。

→ [グラフを確認する](https://mackerel.io/my/hosts)


## <a name="5">5. プラグインのインストール・設定・挙動の確認</a>
### 【手順９】公式プラグイン集を確認する

Mackerel の公式プラグイン集は [https://github.com/mackerelio/mackerel-agent-plugins](https://github.com/mackerelio/mackerel-agent-plugins) で公開されています。
OSS（オープンソースソフトウェア）なので、いつでも誰でも実装を確認できますし、修正も追加も可能です。

現時点でどのようなプラグインがあるのか、確認してみましょう。

### 【手順10】公式プラグインをインストールする

以下のコマンドを実行し、公式プラグイン集をインストールします。

<div class="clip">
  <pre><code class="target">sudo yum install -y mackerel-agent-plugins</code></pre>
  <button type="button" class="clip-button">Copy</button>
</div>

コマンドを実行すると画面には色々と表示されると思いますが、最終的に「完了しました！」と表示され、再びコマンドが入力できる状態になっていれば成功です。

### 【手順11】設定ファイルへのプラグイン設定の追記

以下のコマンドを実行することで、mackerel-agent の設定ファイル `/etc/mackerel-agent/mackerel-agent.conf` にプラグインを利用するための設定を追記します。

<div class="clip">
  <pre><code class="target">sudo sh << SCRIPT
cat >>/etc/mackerel-agent/mackerel-agent.conf <<'EOF';
[plugin.metrics.linux]
command = "mackerel-plugin-linux"
EOF
SCRIPT</code></pre>
  <button type="button" class="clip-button">Copy</button>
</div>

特にエラーなどが発生せず、再びコマンドが入力できる状態になっていれば成功です。（完了メッセージも表示されません）

### 【手順12】エージェントを再起動する

以下のコマンドにより mackerel-agent を再起動します。

<div class="clip">
  <pre><code class="target">sudo systemctl restart mackerel-agent</code></pre>
  <button type="button" class="clip-button">Copy</button>
</div>

コマンド実行後、 `[ OK ]` と表示されていれば起動成功です。

### 【手順13】プラグインを手動で実行してみる

本来はエージェントに組み込み、エージェントが実行するプラグインですが、人の手で実行することも可能です。
以下のコマンドにより実行してみて、どのような結果が得られるか確認してみましょう。

<div class="clip">
  <pre><code class="target">sudo mackerel-plugin-linux</code></pre>
  <button type="button" class="clip-button">Copy</button>
</div>

## <a name="6">6. 便利な使い方のご紹介</a>
### 【手順14】Mackerel 公式ドキュメントの確認

Mackerel では、ドキュメントの充実にも力を入れています。
ぜひ一度確認してみてください。これから Mackerel を始める人にも、普通の使い方では物足りない人にも、おすすめの内容となっています。

- [Mackerelヘルプ](https://mackerel.io/ja/docs)
- [Mackerel API ドキュメント](https://mackerel.io/ja/api-docs/)


### 【手順15】ハンズオンで監視したサーバーを管理対象から外す

今回使ったサーバーは、セミナー終了後にシャットダウンします。

今の状態のままシャットダウンしてしまうと、監視ルール「connectivity」に抵触することになり、参加者のみなさんにメール通知が送信されてしまいます。
そのため、今回使ったサーバを Mackerel の管理対象から外す作業をお願いします。

[ホスト一覧画面](https://mackerel.io/my/hosts)から今回使用したサーバーの情報を選び、スライドの手順に従って下さい。

# 参考情報

- [Mackerel](https://mackerel.io/)
- [Mackerelヘルプ](https://mackerel.io/ja/docs)
- [Mackerel API ドキュメント](https://mackerel.io/ja/api-docs/)
- [Mackerel ユーザーグループ ブログ](http://mackerel-ug.hatenablog.com/)

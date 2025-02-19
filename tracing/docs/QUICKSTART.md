# 事前準備のお願い

本日は「**わかった気になる分散トレーシング - OpenTelemetryでトレーシングに入門するハンズオン！**」にご参加いただき、誠にありがとうございます。

このハンズオンでは、皆さまがお持ちのコンピュータで実際に手を動かしながら分散トレーシングを体験いただきます。

時間の関係上、進行をスムーズにするために、資料の説明順序と若干変わりますが、以下の手順を事前にご準備いただけますよう、よろしくお願いいたします。

1. **ガイドの準備**<br/>ブラウザでGitHubのページ [https://github.com/mackerelio/mackerel-handson](https://github.com/mackerelio/mackerel-handson) を開き、さらに「tracing」→「docs」と進んでください。URLとしては [https://github.com/mackerelio/mackerel-handson/tree/main/tracing/docs](https://github.com/mackerelio/mackerel-handson/tree/main/tracing/docs) となります。
1. **Gitの設定**<br/>ターミナル（またはコマンドプロンプトなど）で、「`git --version`」を実行したときに、バージョンが表示されますか？ もしバージョンではなく`command not found`のように表示された場合、`git`コマンドがインストールされていないものと思われます。「[Gitの設定](01-prepare/README.md#git%E3%81%AE%E8%A8%AD%E5%AE%9A)」をご覧いただき、セットアップしてください。
1. **Dockerの設定**<br/>ターミナル（またはコマンドプロンプトなど）で、「`docker run --rm hello-world`」を実行したときに、「`Hello from Docker!`」のようなメッセージが表示されますか？ `command not found`のように表示された場合、`docker`コマンドがインストールされていないものと思われます。「[Dockerの設定](01-prepare/README.md#docker%E3%81%AE%E8%A8%AD%E5%AE%9A)」をご覧いただき、セットアップしてください。<br/>`docker`コマンドはインストールされているにもかかわらず（`docker --version`でバージョンが表示される）、エラーメッセージが出ているときには、ご相談ください。
1. **Mackerelオーガニゼーションの用意**<br/>Mackerelのオーナーまたは管理者権限を持つオーガニゼーションをご用意しており、Mackerelのサインインが済んだ状態になっていますか？ まだサインアップしていない、サインアップは済んでいるがサインインしていない、オーナーや管理者権限のオーガニゼーションを用意していない場合は、「[Mackerelを使うための準備](02-mackerelsetup/README.md#mackerel%E3%82%92%E4%BD%BF%E3%81%86%E3%81%9F%E3%82%81%E3%81%AE%E6%BA%96%E5%82%99)」をご覧いただき、ユーザーサインアップやオーガニゼーションの用意をしてください。<br/>ユーザーの作成や、トライアル期間のオーガニゼーションの利用では課金は発生しませんのでご安心ください。
1. **ハンズオンのGitリポジトリの展開**<br/>ターミナル（またはコマンドプロンプトなど）で書き込み可能な作業フォルダに`cd フォルダパス名`のコマンドで移動し、`git clone https://github.com/mackerelio/mackerel-handson.git`で展開してください。「[Gitリポジトリの展開](05-hotrod1/README.md#git%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%81%AE%E5%B1%95%E9%96%8B)」もご参照ください。<br/>もし以前にこのGitリポジトリを展開済みの場合は、`mackerel-handson`フォルダ内で`git checkout main`と`git pull`を実行し、最新の状態にしておいてください。
1. **APIキーの取得とenv.txtファイルの変更**<br/>「[MackerelのAPIキーの取得とenv.txtファイルの変更](05-hotrod1/README.md#mackerel%E3%81%AEapi%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97%E3%81%A8envtxt%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AE%E5%A4%89%E6%9B%B4)」をご覧いただき、手順に従って進めてください。<br/>具体的には、Mackerelのオーガニゼーションのサイドメニューからオーガニゼーション名をクリックし、さらに「APIキー」タブをクリックします。デフォルトで1つAPIキーが用意されているので、コピーボタン（「編集」の左側にあるボタン）をクリックしてコピーしてください。<br/>さらに、展開した`mackerel-handson`フォルダ内の`tracing`→`demo`の中にある`env.txt`をテキストエディタで開き、「`MACKEREL_APIKEY=`」の後ろに、コピーしたAPIキーの内容をペーストして保存してください。
1. **デモアプリケーションの起動テスト**<br/>「[Dockerの実行](05-hotrod1/README.md#docker%E3%81%AE%E5%AE%9F%E8%A1%8C)」をご覧ください。ターミナル（またはコマンドプロンプトなど）で、`mackerel-handson/tracing/demo/hotrod`フォルダに`cd フォルダパス名`のコマンドで移動し、`docker compose up`で起動してください。<br/>「`http://localhost:8080`」をブラウザで開き、「Hot R.O.D.」というデモアプリケーションが開くことを確認できたでしょうか？<br/>実行していたアプリケーションは、`docker compose up`のターミナル（またはコマンドプロンプトなど）でCtrlキーを押しながらCキーを押すことで停止できます。さらに`docker compose down`でコンテナを削除してください。
1. **アプリケーションのビルドとデータベース初期化**<br/>「[アプリケーションのビルドとデータベースの初期化](12-prepare-webapp/README.md#アプリケーションのビルドとデータベースの初期化)」をご覧ください。ターミナル（またはコマンドプロンプトなど）で、`mackerel-handson/tracing/demo/sample-app/ruby`フォルダに`cd フォルダパス名`のコマンドで移動し、`docker compose run --rm app bin/rails db:prepare`を実行してください。特にエラーなく終了すれば問題ありません。

手順が不明またはうまくいかない場合は、ご相談ください。

**ご協力ありがとうございます！**

# 事前準備のお願い

**本日のハンズオンの進行をスムーズにするため、ハンズオン開始の前に以下をご準備ください。**

1. [Gitの設定](01-prepare/README.md#git%E3%81%AE%E8%A8%AD%E5%AE%9A)。`git`コマンドがターミナル上で動作するようにしておいてください。
1. [Dockerの設定](01-prepare/README.md#docker%E3%81%AE%E8%A8%AD%E5%AE%9A)。`docker`コマンドが動作し、`hello-world`コンテナが実行できることも確認してください。
1. [Mackerelを使うための準備](02-mackerelsetup/README.md#mackerel%E3%82%92%E4%BD%BF%E3%81%86%E3%81%9F%E3%82%81%E3%81%AE%E6%BA%96%E5%82%99)。Mackerelのユーザー登録および、オーナーまたは管理者の権限を持つオーガニゼーションをご用意ください。新規にお作りいただくこともできます（費用はかかりません）。
1. [Gitリポジトリの展開](05-hotrod1/README.md#git%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%81%AE%E5%B1%95%E9%96%8B)。事前にハンズオンのGitリポジトリ `https://github.com/mackerelio/mackerel-handson.git` を`git`コマンドで展開してください。すでに展開済みの方は、`git checkout main`、`git pull`を実行して最新の状態にしておいてください。
1. [MackerelのAPIキーの取得とenv.txtファイルの変更](05-hotrod1/README.md#mackerel%E3%81%AEapi%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97%E3%81%A8envtxt%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AE%E5%A4%89%E6%9B%B4)。事前に`tracing/demo-hotrod/env.txt`にオーガニゼーションのAPIキーを書き込んでください。
1. [Dockerの実行](05-hotrod1/README.md#docker%E3%81%AE%E5%AE%9F%E8%A1%8C)。ターミナルで`tracing/demo-hotrod`フォルダ内に移動し、Dockerコンテナを起動してみてください。[http://localhost:8080](http://localhost:8080)をブラウザで開いて、HotRODアプリケーションの画面が表示されることを確認してください。
1. [アプリケーションのビルドとデータベースの初期化](12-prepare-webapp/README.md#アプリケーションのビルドとデータベースの初期化)。コンテナイメージの取得、アプリケーションのビルドとデータベースの初期化をしておいてください。

**ご協力ありがとうございます！**

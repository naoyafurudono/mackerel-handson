# わかった気になる分散トレーシング - OpenTelemetryでトレーシングに入門するハンズオン

このハンズオンでは、皆さんのコンピュータ上に構築した仮想環境コンテナでアプリケーションを動かし、アプリケーションから得られたOpenTelemetryトレースシグナルをオブザーバビリティプラットフォームの[Mackerel](https://ja.mackerel.io)に送って、解析することを体験します。

構成は以下のとおりです。

1. [このハンズオンを始める前の準備](01-prepare/README.md)
1. [Mackerelを使うための準備](02-mackerelsetup/README.md)
1. [分散トレーシングとは](03-distributedtracing/README.md)
1. [OpenTelemetryとは](04-opentelemetry/README.md)
1. [HotRODデモを使ってトレースシグナルを送ってみよう 〜デモ環境をDockerで構築する](05-hotrod1/README.md)
1. [HotRODデモを使ってトレースシグナルを送ってみよう 〜送信したトレースをMackerelで見る](06-hotrod2/README.md)
1. [HotRODデモを使ってトレースシグナルを送ってみよう 〜レイテンシー悪化の原因を調査する](07-hotrod3/README.md)
1. [HotRODデモを使ってトレースシグナルを送ってみよう 〜パフォーマンスを改善する](08-hotrod4/README.md)
1. [HotRODデモを使ってトレースシグナルを送ってみよう 〜エラーの原因の解析](09-hotrod5/README.md)
1. [ここまでのまとめ](10-hotrod-summary/README.md)
1. [トレースを用いてWebアプリケーションを改善してみよう](11-handson-intro/README.md)
1. [トレースを用いてWebアプリケーションを改善してみよう 〜サンプルWebアプリケーションの準備](12-prepare-webapp/README.md)
1. [トレースを用いてWebアプリケーションを改善してみよう 〜OpenTelemetryによる計装](13-instrumentation/README.md)
1. [トレースを用いてWebアプリケーションを改善してみよう 〜Mackerelでトレースを確認しよう](14-mackerel-tracing/README.md)
1. [トレースを用いてWebアプリケーションを改善してみよう 〜シナリオ1](15-scenario1/README.md)
1. [トレースを用いてWebアプリケーションを改善してみよう 〜シナリオ2](16-scenario2/README.md)
1. [トレースを用いてWebアプリケーションを改善してみよう 〜シナリオ3](17-scenario3/README.md)
1. [トレースを用いてWebアプリケーションを改善してみよう 〜まとめ](18-wrapup/README.md)

このハンズオンを終えたあとには、複数のサービスから構成されるアプリケーションに対し、OpenTelemetryに準拠した分散トレーシングがどのように活用できるかわかるでしょう！

## ご注意
本ハンズオンドキュメントに記載された内容の全部または一部を、当社の許可なくほかの目的で使用、複製、転載、改変、配布することを禁止します。本ドキュメントの内容を流用する必要がある場合は、事前に当社の書面による承諾を得てください。

[→「このハンズオンを始める前の準備」に進む](01-prepare/README.md)

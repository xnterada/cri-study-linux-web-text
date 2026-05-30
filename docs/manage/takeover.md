# カリキュラム引継ぎ資料

本資料は、Linuxカリキュラム用アプリの引継ぎを目的としています。

## 1. 事前準備

### 用意するもの

1. AWSアカウント
2. IAMユーザ（管理者権限を付与しておくこと）
3. ドメイン（Route53で取得を推奨。「.click」ドメインが安価でおすすめ）
4. ホストゾーン（Route53で作成しておくこと）
5. GitHubアカウント（ソースコード管理とCDに使用）
6. DBバックアップファイル（前任者から提供します）

### AWS CLIのインストールと設定

以下の手順でAWS CLIをインストールし、認証設定を行う。[公式ドキュメント](https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/getting-started-install.html)を参考にすること。

認証設定にはconfigureコマンドを使用して、AWSアクセスキーIDとシークレットアクセスキーを入力する。
```bash
aws configure
```
TerraformとPackerもこのクレデンシャルファイルを使用してAWSリソースにアクセス可能となる。

### Terraformのインストール

自身のOSに合わせてTerraformを[公式ドキュメント](https://developer.hashicorp.com/terraform/install)を参考にインストールする。

## Packerのインストール

自身のOSに合わせてPackerを[公式ドキュメント](https://developer.hashicorp.com/packer/install)を参考にインストールする。

## リポジトリのクローンと自分のGitHubアカウントへのフォーク
以下のリポジトリをクローンし、自分のGitHubアカウントにコピーする。
（注意）この資料内での「コピー」とは、自分のローカルにクローンした後、.gitディレクトリを削除してから、自分のGitHubアカウントに新規リポジトリを作成し、そこにコードをプッシュすることを指すこととする。

- [テキスト教材リポジトリ](https://github.com/xnterada/cri-study-linux-web-text)
- [アプリリポジトリ](https://github.com/xnterada/cri-study-linux-web-app)
- [AMIリポジトリ](https://github.com/xnterada/cri-study-linux-web-app-ami-sample)
- [Terraformリポジトリ](https://github.com/xnterada/cri-study-linux-web-app-infla-sample)

再プッシュするときは「-sample」のサフィックスを消すなど、自由にリポジトリ名を変更してもらって構わない。

## 2. インフラ構築

### PackerでAMIを作成
Packerを使用して、アプリを起動するEC2インスタンス用のAMIを作成する。
詳細は[AMIリポジトリ](https://github.com/xnterada/cri-study-linux-web-app-ami-sample)のREADMEを参照。

### Terraformでインフラ構築
Terraformを使用して、アプリインフラを構築する。
詳細は[Terraformリポジトリ](https://github.com/xnterada/cri-study-linux-web-app-infla-sample)のREADMEを参照。

## 3. アプリデプロイ
GitHub Actionsを使用して、アプリをデプロイする。
詳細は[アプリリポジトリ](https://github.com/xnterada/cri-study-linux-web-app)のREADMEを参照。

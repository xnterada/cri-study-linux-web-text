# カリキュラム引継ぎ資料

## 用意するもの

- AWSアカウント
- IAMユーザ（管理者権限を付与しておくこと）
- ドメイン（Route53で取得を推奨。「.click」ドメインが安価でおすすめ）
- ホストゾーン（Route53で作成しておくこと）
- DBバックアップファイル

## AWS CLIのインストールと設定

以下の手順でAWS CLIをインストールし、認証設定を行う。
https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/getting-started-install.html

## AWS CLI認証設定

AWSのリソースにアクセスするためにクレデンシャル設定を行う。
TerraformとPackerもこのクレデンシャルファイルを使用してAWSリソースにアクセス可能となる。

```bash
mkdir -p ~/.aws
echo "[default]" > ~/.aws/credentials
echo "aws_access_key_id = YOUR_ACCESS_KEY_ID" >> ~/.aws/credentials
echo "aws_secret_access_key = YOUR_SECRET_ACCESS_KEY" >> ~/.aws/credentials
```

## Terraformのインストール

自身のOSに合わせてTerraformを以下の手順を参考にインストールする。
https://developer.hashicorp.com/terraform/install

## Packerのインストール

自身のOSに合わせてPackerを以下の手順を参考にインストールする。
https://developer.hashicorp.com/packer/install

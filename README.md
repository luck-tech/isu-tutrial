# ISUCON13 (ISUPipe)

## 問題に関連するリンク

[ISUCON13 当日マニュアル](https://github.com/isucon/isucon13/blob/main/docs/cautionary_note.md)
[ISUPipe アプリケーションマニュアル](https://github.com/isucon/isucon13/blob/main/docs/isupipe.md)
[ISUCON初心者向け講習会資料](https://isucon-workshop.trap.show/)

## アプリのディレクトリ構造

/home/isucon/webapp/
├── go # Go実装
├── sql # データベースのスキーマおよび初期化に必要なSQL
└── pdns # PowerDNSの設定

## その他ISUCONで使いそうなファイルの場所

/home/isucon/env.sh # 環境変数の設定ファイル
/etc/nginx/ # Nginxの設定ディレクトリ
/etc/mysql/ # MySQLの設定ディレクトリ
/etc/systemd/system/isupipe.go.service # アプリケーションのsystemdサービスファイル
/etc/nginx/tls/ # SSL証明書

## ベンチマーク実行

```sh
ssh isu "sudo -i -u isucon ./bench run --enable-ssl"
```

## サーバー接続

```sh
ssh isu  # 35.76.120.249 (ユーザ: isucon)
```

## ブラウザ確認

https://pipe.u.isucon.local/ (自己署名証明書のため警告あり)

test001 testでログイン

## 注意事項

- ドメインは本番の _.u.isucon.dev → _.u.isucon.local に変更されている
- SSL証明書は自己署名
- 本番構成: c5.large (2vCPU, 4GB RAM) × 3台、今回は1台構成

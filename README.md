# HomePage

## 概要
阿部寛Likeなホームページです

https://izmyuta.com/

## 工夫したポイント
- 本家のページと同様、軽さを重視した
  - HTMLとCSSだけのシンプルなページ
  - CloudFrontを使ってCDNを構築することでさらに高速化
- ipv6通信にも対応
  - 最近何かと話題なので
  - DNSにレコード追加するだけだったのでそこまで難しくなかった

## 大変だったポイント
- S3：パブリックアクセスのセキュリティをガチガチに固めるとGitHub Actionsでデプロイできなくなった
  - CloudFrontからのアクセスに限定したいので、パブリックアクセスは拒否したいが、ワークフローも維持しておきたい...
  - 何かいい方法あったら教えてください 🙏
- CloudFront：S3バケットが更新されても、CloudFrontに反映されない
  - キャッシュが残っていたことが原因。キャッシュポリシーを変更して対応。

## サービス構成図
![](aws.png)

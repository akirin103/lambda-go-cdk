## lambda-go-cdk
ランタイムにGo言語を使用したAWSLambdaをAWSCDK経由でデプロイする実験用リポジトリ。

<br />

### 参考＆メモ

[Go構造体の`json:hoge`の正体を探る](https://qiita.com/Syuparn/items/9e6fb68afb5418893c23)

[.zip ファイルアーカイブを使用して Go Lambda 関数をデプロイする](https://docs.aws.amazon.com/ja_jp/lambda/latest/dg/golang-package.html)

#### zipで手動デプロイする
```
# GitHub から lambda ライブラリをダウンロードします。
$ go get github.com/aws/aws-lambda-go/lambda

# 実行可能ファイルをコンパイルします。
$ GOOS=linux go build main.go

# 実行可能ファイルを .zip ファイルにパッケージ化して、デプロイパッケージを作成します。
$ zip function.zip main
```

### 問題点
2022/05/05(木)時点では、AWSコンソール上でGo1.xランタイムで稼働するLambdaのソースコードのインライン編集ができない。

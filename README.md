# melos_monorepo

## モノレポ 構造 
１つのリポジトリに複数のプロジェクトを格納

### メリット
・共有モジュールを楽に使用 
 
・Lintなどを扱いやすい 

・ライブラリのバージョン管理が楽

### 利用技術
・ Melos 


パッケージの管理

 ・ Dart Frog

 
 BFF の実装


 
 

## BFF 構築
 フロントエンドの要件に合わせて最適化されたAPIやデータを提供する

 
 バックエンドシステムの複雑さの隠蔽

EX)


![image](https://github.com/rensawamo/melos_monorepo/assets/106803080/c13118bf-8acd-442d-8f27-4032a03521a8)




## セットアップ
以下のコマンドを実行
```sh
dart pub global activate melos
```

pubspec.yaml ファイルを編集する
```sh
name: YOURAPP
environment:
  sdk: ">=2.18.0 <3.0.0"
dev_dependencies:
  melos: ^3.1.1
```

以下のコマンドを実行
```sh
dart pub add melos --dev
```

melos.yaml ファイルを作成しコマンド実行のスクリプトを記述する
```sh
name: YOURAPP

packages:
  - packages/*

scripts:

```

Dart Frogのインストール(https://dartfrog.vgv.dev/)
```sh
dart pub global activate dart_frog_cli
```

packages フォルダに移動し 以下コマンドを実行する
```sh
cd packages
dart_frog create backend
```

backend フォルダに移動し 以下コマンドを実行し。  http://localhost:8080 を立ち上げる
```sh
cd  backend 
dart_frog dev
```

packeages ディレクトリに移動し 以下のコマンドを実行し、frontend ディレクトリを作成する
```sh
flutter create frontend
```


以下コマンドを実行し、shared ディレクトリを作成する
```sh
dart create -t package shared
```

ここでこれらの依存関係を示す必要がある
backend frontend ディレクトリ のそれぞれの pubspec.yamlのファイルのdependeciesに shared を追加
```sh
dependencies:
  dart_frog: 1.2.2
  shared: 1.0.0
```

ルートディレクトリに移動し 以下コマンドを実行する
```sh
melos bs
``` 


![image](https://github.com/rensawamo/melos_monorepo/assets/106803080/e721af7c-83b3-430f-a6db-e77a6d8dd27f)




## ディレクトリ間の依存関係
packages/backend に移動し以下のコマンドを入力
```sh
flutter pub get 
```


以下のようになれば set up 完了


![image](https://github.com/rensawamo/melos_monorepo/assets/106803080/dd3f2661-c625-4afc-9507-2f8ac3ffa00b)

















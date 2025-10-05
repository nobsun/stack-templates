# stack-templates

## atcoder.hsfiles

これは、HaskellでAtCoderを楽しむためのStackのテンプレートファイルです。

### 利用のための前提

作者の環境は以下のとおりで、この環境で確認しました。とはいえ、見落しがあるかもしれません。

- OS： Pop!_OS 24.04 LTS Beta （Ubuntu 24.04 LTS 土台になっている）
- Haskell ツール （以下がインストール済みであること）
    - GHCup 0.1.50.2
        - Stack 3.3.1
        - HLS 2.10.0.0
        - cabal 3.12.1.0
        - GHC 9.8.4
- AtCoder ツール （以下がインストール済みであること）
    - online-judge-tool
    - atcoder-cli
    - aclogin

AtCoder ツールについては、以下の記事が判りやすいです。

https://zenn.dev/ok_xmonad/articles/ae1c5bf0a955c1

~/.config/atcoder-cli-nodejs/haskell/template.json はこの記事と同じように設定されていることを前提とします。

さらに、AtCoder へのログインについては、以下のツールが必要なようです。

https://github.com/key-moon/aclogin/blob/main/README.md#aclogin

この README にあるように、AtCoder に Browser でログインしたあとの Cookie を ~/.config/atcoder-cli-nodejs/session.json に設定しておく必要があります。

## AtCoder用 Stack テンプレートの使い方

### プロジェクト初期化

```shell
$ stack new abc426 nobsun/atcoder ## 筆者の作成したテンプレートファイルの利用
$ cd abc426
$ source activate ## ユーティリティスクリプトの実行権限 ON
$ ./initializing  ## プロジェクトディレクトリの（再）構成、テスト用サンプルデータの取得
```

### 問題A用の初期化

```shell
$ ./resetting a ## 問題A用初期設定、このあと app/a/Main.hs を編集する
```

### 問題Aを解くコード`app/a/Main.hs`のビルドとサンプルデータによるテスト

```shell
$ ./checking ## app/a/Main.hs のコンパイルと動作チェック
```

### 問題Aを解くコード`app/a/Main.hs`の提出

**N.B.** コンテスト開催時間中のみ CLI で提出可能

```shell
$ ./submitting ## app/a/Main.hs の提出
```

# boost ビルドプロジェクト

## 概要

CODIANZ で使用する boost C++ ライブラリを使用するためのプロジェクトです。このプロジェクトで ios と android のビルドが行えます。

ビルドが必要なライブラリで、このプロジェクトでびるどするものは下記のとおり。
* atomic
* chrono
* date_time
* regex
* timer
* thread
* filesystem
* system

一部は、std に標準採用されているものもあるが、複数のビルド環境で同一のライブラリを使用することで機種依存を吸収する方針。しかし、一部、標準かboostかの境界線が曖昧なものも正直あるが、そこは個人的な歴史的背景があるので勘弁。

必要がれば build.sh の ```BOOST_BUILD_LIBRARIES``` にライブラリを追加すれば動く筈です。（一部、他のライブラリに依存するものがあるけど、ここでは省略）

なお、このプロジェクトは Git LFS (Large File Storage) を使用しています。Git LFSのインストールについては下記 URL で確認してください。
https://git-lfs.github.com/


## 使用方法

```sh
$ ./build.sh (ios|android)
```

## iOS ビルド準備

ビルドで使用する Xcode を指定します。
```sh
$ sudo xcode-select --switch  /Applications/Xcode.10.3.app
```

## ビルド方法

```sh
$ ./build.sh version target [build]
```

|パラメータ|必須|摘要|例|
|-|:-:|-|-|
|version|○|boost バージョン|1.69.0|
|target|○|ビルドターゲット（ios \| android \| all）|ios|
|build| |ビルドする場合指定。ビルド済みライブラリを展開する場合は未指定。|build|



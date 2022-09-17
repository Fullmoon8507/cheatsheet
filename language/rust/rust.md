# 基本
## コメント
* 一行のコメントは//
* 複数行のコメントは/* */

## 式と文
* 式(expression): 何かしらの値を返す。
* 文(statement): 処理を実行するが、値は返さない。

## ブロック
* スコープを作成。
* 文をいくつも記述できる。
> { statement; statement; ...; (expression) }

## オブジェクト
* 数値や関数や参照など、すべてオブジェクト。

## 所有権
* (後で記載)

## 束縛
* (後で記載)

## 参照
* (後で記載)

## 可変性
* (後で記載)

# cargoコマンド
## プロジェクト作成
| コマンド | 内容 |
| -------- | ---- |
| cargo new {project name} | バイナリプロジェクトを作成 |
| cargo new --lib {lib name} | ライブラリプロジェクトを作成 |

## キャッシュ削除
| コマンド | 内容 |
| -------- | ---- |
| cargo clean | キャッシュを削除 |

 ※「 Blocking waiting for file lock on package cache」となったら上記のコマンドを実行。それでもだめなら、以下のコマンドを実行。
 * rm -rf ~/.cargo/registry/index/*
 * rm -rf ~/.cargo/.package-cache

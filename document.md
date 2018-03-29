# addコマンドについて

* gitで変更管理するファイルとして追加するコマンド
  * ディレクトリに追加するだけではgit上で管理することにならない
  * どのファイルを追加するかは任意で選択できる
  * 削除内容をステージングするには -u オプションをつける

# initコマンドについて

* git上で管理させたいフォルダを追加するコマンド
  * 管理したいフォルダ内で実行するとそのフォルダ内に.gitというフォルダが作成され、以降、gitの管理対象となる

# commitコマンドについて
  * ファイルの変更や追加をリポジトリに保存するコマンド。

  * 文法
  ```
  git commit
  git commit -m 'commit comment'
  ```
* 文法
```
git commit
git commit -m 'commit comment'
```

# commit -aコマンドについて
* 変更されたファイル(新規を除く)をインデックスに追加し,コミットするコマンド

# pushコマンドについて

* commit後にローカルの変更をサーバー上へ反映（アップロード）することをpushという
  * -f をつけるとローカルの状態を強制的にサーバー上へ反映するので使い方は要注意

# cloneコマンドについて

* リモートリポジトリの内容をローカルにコピーするためのコマンド
  * git clone [リモートリポジトリパス]と入力する
  * リモートリポジトリのパスの拡張子は.git
  * 通常はmasterブランチを持ってくるが、以下コマンドでブランチ指定が可能

```
git clone -b [ブランチ名] --single-branch [リモートリポジトリ名]
```

# remote: Counting objects: 12, done.
> remote: Compressing objects: 100% (10/10), done.
remote: Total 12 (delta 3), reused 11 (delta 2), pack-reused 0
Unpacking objects: 100% (12/12), done.
From https://github.com/shigesan1019/gbc
   66e449d..84d0e59  master     -> origin/master
Updating 66e449d..84d0e59


# cherry-pickについて
* cherry-pick コミットIDでそのコミットを反映させることができる
  * 特定のコミットの内容を反映させたいときに使う。主にバグ修正など
  * git log などで特定のコミットIDを確認して実行する
```
git cherry-pick 546de2cc727fcae02646c6af637f401e4238feef
```

# checkout について
* checkout
ブランチを変更する。
```
git checkout [branch名]
```

* chekout -b
リモートの中身を新しいローカルブランチを作成
```
git checkout -b new-branch origin/master
```
* コンフリクトした時、どちらか一方を全面的に採用したい場合
```
# fileA.txt を現在チェックアウトしているブランチ側の対応に合わせる場合
 git checkout --ours fileA.txt
 git add fileA.txt    # add を忘れずに

# fileB.txt をマージさせたブランチ側に合わせる場合
 git checkout --theirs fileB.txt
 git add fileB.txt

$ git commit
```

# rebaseコマンドについて
* 一方のブランチにコミットされたすべての変更をもう一方のブランチで再現する（＝コピーする）
* masterを一直線にし、fast forwardをできるようにする、等の用途で用いることができる

  ```
  git rebase master
  git rebase --onto master server client
  git rebase -i コミットid
  git rebase --abort
  ```

** -i
細かいcommitをまとめて、1つの大きめのコミットとする
コミットidは、リベースしたいところの1つ前を指定する。
** --abort
間違ったrebaseを削除する

# pullコマンドについて
* リモートリポジトリの変更を取り込むコマンド

  ```
  git pull [remote repository PATH] [branch]
  ```

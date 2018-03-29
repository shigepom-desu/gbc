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

# commit -aコマンドについて
* 変更されたファイル(新規を除く)をインデックスに追加し,コミットするコマンド

# cloneコマンドについて

* リモートリポジトリの内容をローカルにコピーするためのコマンド
  * git clone [リモートリポジトリパス]と入力する
  * リモートリポジトリのパスの拡張子は.git
  * 通常はmasterブランチを持ってくるが、以下コマンドでブランチ指定が可能
* 文法
``` git commit
``` git commit -m 'commit comment'


# remote: Counting objects: 12, done.
> remote: Compressing objects: 100% (10/10), done.
remote: Total 12 (delta 3), reused 11 (delta 2), pack-reused 0
Unpacking objects: 100% (12/12), done.
From https://github.com/shigesan1019/gbc
   66e449d..84d0e59  master     -> origin/master
Updating 66e449d..84d0e59

'''git clone -b [ブランチ名] --single-branch [リモートリポジトリ名]

```
git clone -b [ブランチ名] --single-branch [リモートリポジトリ名]
```
# rebaseコマンドについて
* 一方のブランチにコミットされたすべての変更をもう一方のブランチで再現する（＝コピーする）
* masterを一直線にし、fast forwardをできるようにする、等の用途で用いることができる
  ```
  git rebase master
  git rebase --onto master server client

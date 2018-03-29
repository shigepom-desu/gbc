# addコマンドについて

* gitで変更管理するファイルとして追加するコマンド
  * ディレクトリに追加するだけではgit上で管理することにならない
  * どのファイルを追加するかは任意で選択できる
  * 削除内容をステージングするには -u オプションをつける

# commitコマンドについて
  * ファイルの変更や追加をリポジトリに保存するコマンド。

  * 文法
  ```
  git commit
  git commit -m 'commit comment'
  ```
* 文法
``` git commit
``` git commit -m 'commit comment'

間に行を追加してみた

# cloneコマンドについて

* リモートリポジトリの内容をローカルにコピーするためのコマンド
  * git clone [リモートリポジトリパス]と入力する
  * リモートリポジトリのパスの拡張子は.git
  * 通常はmasterブランチを持ってくるが、以下コマンドでブランチ指定が可能



```
git clone -b [ブランチ名] --single-branch [リモートリポジトリ名]
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


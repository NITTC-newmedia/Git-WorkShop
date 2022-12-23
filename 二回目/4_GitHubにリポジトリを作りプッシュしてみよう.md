# プッシュって?
ローカルリポジトリ(自分のpc内のリポジトリ)の変更内容をリモートリポジトリ(GitHubの方のリポジトリ)に反映すること。
コマンドを打つだけでGitHubのリポジトリにコードを上げれるので便利。

# プルって?
プッシュと逆の操作。リモートリポジトリの変更内容をローカルリポジトリに取り込むこと。プッシュとプルを使うことで、コマンドでの操作だけでGitHubの操作ができる。

# 早速GitHubのリポジトリにプッシュ
## まずは、GitHubにプッシュする先のリモートリポジトリを作る
1. [GitHubのサイト](https://github.com)に行き、アカウントにログイン。
2. 右上の＋ボタンから「New repository」を選択。
3. リポジトリ作成画面に移るので、「Repository name」というところに「git-test」と入力。これがリポジトリ名になる。
4. 他の項目はいじらずに、「Create repository」のボタンをクリック。
5. これでGitHubのリポジトリの準備は完了。

## プッシュする準備
今作成したリモートリポジトリにプッシュするための前準備をする。ターミナルに戻り次のコマンドを実行する。

```bash
$ git remote add origin git@github.com:Your_Name/git-test.git # Your_Nameのところには自分のGitHubのアカウント名を入力する

$ git remote -v # リモートを設定できたか確認
origin git@github.com:Your_Name/git-test.git (fetch)
origin git@github.com:Your_Name/git-test.git (push)
```

これでリモートを設定できたので、プッシュすることができる。

## プッシュ!!
```git push```コマンドでリモートリポジトリにローカルリポジトリの内容を反映。今現在いるブランチの内容が反映される。
```bash
$ git push origin main # リモートのmainブランチに変更を反映
```
先ほどから出てくる```origin```とは、リモートリポジトリを指す。

例: <br>```main``` -> ローカルの```main```ブランチ<br>```origin main``` -> リモートの```main```ブランチ

## ※エラーが出てプッシュできない時
```bash
$ git push origin main
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

```
というエラーが出た場合、Windowsユーザーは[こちらの記事](https://qiita.com/ebtiag/items/9b1d0f78ca23c1ccf3b9)、Macユーザーは[こちらの記事](https://qiita.com/ucan-lab/items/e02f2d3a35f266631f24)を参照して、公開鍵を登録してプッシュしてください。

## GitHubでの変更内容をプルしてみる
まず、リモートリポジトリの方の```test_1.txt```ファイルを手動で編集する。

```txt:test_1.txt
ねこ
```

```ねこ```と入力し、ページ下の```Commit changes```というボタンを押して保存(コミット)。

次にターミナルに戻り、```git pull```コマンドを実行する。

```bash
$ git pull
```
すると変更をローカルに取り込むことができる。
試しにローカルリポジトリの```test_1.txt```を開いてみると、中に「ねこ」と先ほどリモートリポジトリで編集した内容が書いてある。


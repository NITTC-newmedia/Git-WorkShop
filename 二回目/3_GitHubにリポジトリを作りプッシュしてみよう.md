# プッシュって?
リモート(GitHubの方のリポジトリの事)

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
```git push```コマンドでリモートリポジトリにローカルリポジトリの内容を反映。
```bash
$ git push origin main # リモートのmainブランチに変更を反映
```
先ほどから出てくる```origin```とは、リモートリポジトリを指す。

例: <br>```main``` -> ローカルの```main```ブランチ<br>```origin main``` -> リモートの```main```ブランチ

### ※エラーが出てプッシュできない時
```bash
$ git push origin main
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

```
というエラーが出た場合、[こちらの記事](https://qiita.com/ebtiag/items/9b1d0f78ca23c1ccf3b9)を参照して、公開鍵を登録してプッシュしてください。
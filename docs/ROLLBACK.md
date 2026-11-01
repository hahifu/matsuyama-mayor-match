# ロールバック手順（公開を取り消す）

対象: GitHubリポジトリ `hahifu/matsuyama-mayor-match` と、そのGitHub Pages公開。

## 手順A: ページの公開だけを止める（データは残す）

1. リポジトリの Settings → Pages を開く（この操作はリポジトリ所有者が行う）。
2. Source を「None」に変更して保存する。
3. 確認: 公開URL（https://hahifu.github.io/matsuyama-mayor-match/）にアクセスし、404になることを確認する。

## 手順B: リポジトリごと取り消す

1. リポジトリの Settings → General → Danger Zone → Delete this repository を実行する（所有者の操作。確認のためリポジトリ名の入力が求められる）。
2. 確認: リポジトリURLが404になること、PagesのURLも404になること。
3. ローカルの公開パッケージは `~/workspace/matsuyama-mayor-match/repo/` に残っている。再公開する場合はこのフォルダから再度プッシュする。

## 手順C: 内容だけを差し替える（公開は継続）

1. `index.html` を旧版に戻してコミットし、プッシュする。
2. 確認: 公開URLの内容が旧版に戻ったことを、ファイルのハッシュ比較で確認する。

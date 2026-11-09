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

## 追補: 2026-11-09 選挙公報照合修正の差し戻し

対象は index.html の3行（198行目 aria-label、305行目 出典文、393行目 中野氏の子育て・教育欄）。

1. 3行を修正前の文面に戻す。修正前後の文面は `docs/TEST_RECORD.md` の「追補: 選挙公報照合による修正」に記録されている。あわせて同ファイルの追補セクションも差し戻す。
2. `index.html` と `docs/TEST_RECORD.md` をプッシュする。
3. 確認: 公開URLから取得した内容と、差し戻したローカルファイルのハッシュが一致すること。

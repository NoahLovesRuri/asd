
グローバル .gitignore に環境依存のものだけ書く（書く場所はホームディレクトリ）

  # macOS
  .DS_Store

  # RustRover / IntelliJ
  .idea/

これで Mac のゴミファイルと RustRover の IDE 設定はすべて自動で無視されます。 （毎回プロジェクトに書かなくても OK）

---

プロジェクトごとの .gitignore に Rust 共通のものを書く（場所は Cargo.toml がある階層）

  # Rust build
  /target

  # Rust backup
  **/*.rs.bk

これは 公開リポジトリを見た人 に Rust のプロジェクトではこれを無視するのが普通なんだなと分かるので、 リポジトリの中に入れておいたほうが親切です。

---

git init は プロジェクトのルートディレクトリ（Cargo.toml がある場所） で実行します。

  % git init
  Initialized empty Git repository in /Users/noah/My/Rust/asd/.git/

ここで .git フォルダが自動生成され、リポジトリ管理が始まります。

---

GitHub サイトで作成 → 手動で push（HTTPS を使う場合）

  git remote add origin https://github.com/NoahLovesRuri/asd.git
  git branch -M main
  git push -u origin main

もし git push -u origin main でエラーが出たら

  git push -u origin main --force

  注意
  GitHub 上の既存コミット（README の初回コミット等）が消えます。
  自分だけのリポジトリで、過去の履歴を残す必要がない場合のみ使ってください。

---

更新したときの流れ

変更をステージング
  git add .

コミットを作成
  git commit -m "Update some files"

GitHub へ反映
  git push origin main（最初だけ -u を付けていましたが、2回目以降は不要です）

---









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







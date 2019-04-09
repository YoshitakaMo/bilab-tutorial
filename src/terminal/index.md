# Terminal
**ターミナル**とは、キーボード入力と画面の文字表示のみでコンピュータを操作するときに使うアプリケーションです。

このキーボードのみの操作インターフェースのことを一般に **CUI (Character User Interface)** と呼び、ウィンドウやアイコンなどをマウスで操作して、キーボードで文字入力を行うタイプの仕掛けである **GUI (Graphical User Interface)** と区別して呼ばれます。

1980年代前半に Apple 社が Lisa や Macintosh を発表したことで一般にもGUIというものが知られていきましたが、それまでは、コンピュータを使うと言えばCUIのシステムを使っていました。

GUI の利点は、文字だけでなくアイコンなどの絵も表示できて操作できる対象物が明確な点や、マウスで比較的簡単に操作できる点にあります。コンピュータ内の状態や様々な情報を分かりやすく表現し、即座に操作結果が反映されることから一般の人には非常に使いやすいものと言えます。**しかし、大量のファイルを一度に処理したり、複雑な操作を行ったり、それらを連続して処理させる場合などは、非常に使いづらいという欠点があります**。

CUI の場合は、**コマンドを知らないと何も操作できない（ファイルの一覧すら見ることができない）**、操作結果が即座に画面に反映されるとは限らない、など GUI と比べて不便と思える特徴が見受けられます。しかし、**逆にコマンドさえ憶えていれば、複雑な操作や連続した処理も簡単に操作できます**。

## ターミナルの起動
macOSとLinuxの場合は必ずプリインストールされています。macOSの方は[アプリケーション] > [ユーティリティ] > [ターミナル]を選択することでターミナルが起動します。よく使うことになるので、Dockに入れておきましょう。

Linuxの場合も、アプリケーション一覧にターミナルが必ず入っているはずです。または、適当にデスクトップ画面の上で右クリックすると「ターミナルを起動する」メニューがあるので、それを選択することでもターミナルが起動します。

## シェルについて

bashとかzshとかfishとか

## Homebrewを利用したプログラム管理(macOS用)
### インストール方法
**Homebrew**はmacOSで様々なプログラムのインストールを助けてくれる非常に優秀なソフトウェアです。まずは以下のコマンドをターミナルに貼り付けて実行してください。
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
途中質問がいくつか出ますが、Yesと答えればインストールが行われます。

### 基本的な使い方
Homebrewでは*formula*という、Ruby言語で記述されるインストールスクリプトの中にパッケージ定義が書かれています。通常、
`/usr/local/Homebrew/Library/Taps/homebrew/homebrew-core/Formula/`のディレクトリに存在する任意の`foo.rb`ファイルがこれに当たります。ここに存在するプログラムのmacOSへのインストールは、ターミナルを開いて以下のコマンドを打ちます。

```bash
brew install formula
```

すでにインストールされているformulaの一覧を確認するためには

```bash
brew list
```

formulaのバージョン更新は

```bash
brew upgrade formula
```

formulaのアンインストールは

```bash
brew uninstall formula
```
で行います。

他にも様々なコマンドがありますが、詳細な使い方は[こちら](https://github.com/Homebrew/brew/blob/master/docs/Manpage.md)

### インストールしておくべきもの
以下のコマンドで、早めに有用なプログラムをインストールしておきましょう。

```bash
# 基本プログラムコマンド・コンパイラ系
brew install bzip2 gcc gnuplot gnu-sed gawk emacs vim automake autoconf cmake ninja open-mpi parallel python@2 python bash tcsh zsh fish tmux wget
# バイオインフォでよく使う系
brew tap brewsci/bio
brew install blast clustalw clustal-omega fftw hmmer pymol xssp
# その他有用なプログラム
brew install pandoc
```

## XQuartzのインストール(macOSのみ)
Homebrewでインストールした一部のプログラム（PyMOLやグラフ描画ソフトウェアなど）は、GUIを使って操作することを前提としています。この描画エンジンとして、**Xquartz** を入れておきます。

インストール方法は簡単で、https://www.xquartz.org/ にアクセスして XQuartz-2.7.11.dmg をダウンロードし、展開してインストールするだけです。インストールが終わると、[アプリケーション]→[ユーティリティ]の中にXQuartzが入っているはずです。

Linux OSの場合はXQuartzに相当するアプリケーションがはじめからインストールされています。


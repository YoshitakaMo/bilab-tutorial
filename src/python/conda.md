# conda

condaも使うことがあると思うので一応紹介しておきます.
[conda](https://docs.conda.io/en/latest/miniconda.html)は先に紹介した`pipenv`, `pyenv`を統合した仮想環境のようなものです.
そのため, これらのツールとは相性があまり良くなく, condaを使うならこれ一つにしていきましょう.

condaを使う場面は限られていて, condaでないとインストールが難しい, できないライブラリを利用する場合のみです.
というのもcondaは諸悪の根源で, 突如として環境が破壊されることが多く, 非常に扱いにくいからです.
また, condaで入れたnumpyが速いという話もありますが, それを期待して入れるくらいならおとなしく`Julia`か`Rust`を書きましょう.

ということでcondaを入れる際には細心の注意を払うようにしましょう.

## Install

for Mac 🍎, Ubuntu18.04 🐧
```fish
❯ wget https://repo.continuum.io/miniconda/Miniconda3-3.7.0-Linux-x86_64.sh -O ~/miniconda.sh
❯ bash ~/miniconda.sh -b -p $HOME/miniconda
❯ echo 'source (conda info --root)/etc/fish/conf.d/conda.fish' >> ~/.config/fish/config.fish
```

## Usage

まずはじめに仮想環境を作りましょう. 今回は適当に`practice`という名前にします.

```fish
❯ conda create -n practice python=3.7
```

condaの仮想環境はこれで作成されるので, 次に仮想環境に入ってパッケージを追加していきましょう.

```fish
❯ conda activate practice  # conda環境の有効化
❯ conda install jupyter ...  # 必要なパッケージのインストール
```

condaを使うとpipとは違う場所からパッケージをダウンロードし, 依存関係などをよしなにしてくれるので基本的に`conda install`コマンドを用います.
ただ, 中にはcondaでは提供しておらず, pipでないとインストールできないものもあるのでそのような場合にはconda環境が有効になっていることを確認したのち,
`pip install`のコマンドでインストールすることができます.
この辺りは環境が壊れやすい操作ですので注意して行いましょう.

condaで管理したPythonを利用する場合には, パッケージの追加のときと同様,
condaを有効化したのち, pythonの環境を立ち上げることで可能となります.

また, conda環境から抜ける場合には次のコマンドを実行して下さい.

```fish
❯ conda deactivate
```

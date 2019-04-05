# pyenv

[pyenv](https://github.com/pyenv/pyenv)はPython本体ののバージョン管理をするツールです.
2019年現在, 流石にPython2を使うことがあるとは思いたくありませんが,
Python2.7, 3.5, 3.6, 3.7といった複数のバージョンを使わなければならない場面も出てくるかもしれません.

基本的にPythonのバージョンは3.7を使っていきたいところですが, プロジェクトが依存するライブラリが3.6までしか対応していないだとか,
そもそもPython2.7から移行するつもりのないライブラリさえ存在しています.
普通に考えてそのようなライブラリは淘汰されるべきなのですが, 使わなければならない事情もあるでしょう.

そうなったらpyenvの出番です. ただし, まずはpyenvを使わずに実現できないか熟慮し, どうしても必要な時のみ導入するようにしましょう.

## Install

for Mac 🍎, Ubuntu18.04 🐧
``` fish
❯ git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```

本体をインストールしたら環境変数を設定しましょう.

```fish
❯ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
❯ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
❯ echo 'status --is-interactive; and . (pyenv init - | psub)' >> ~/.config/fish/config.fish
```

## Usage

ここでは競技プログラミングのAtcoderが提供する環境であるPython3.4.3をインストールしてみましょう.
ちなみにこのバージョンは非常に古いため, 特定用途以外には決して利用しないでください.
では, 適当な作業ディレクトリを作成していきましょう.

```fish
❯ mkdir competitive_programming; and cd competitive_programming
❯ pipenv install --python 3.4.3
```

このように1度pyenvをインストールしてしまえばpipenvからPythonのバージョンを指定することができるので,
その後あまりpyenvを意識することなく使えてしまうので便利です.

ただし, pyenvに関しては個人で実験, 開発をする場合には必要のないことがほとんどですので,
よく考えて導入しましょう.

# Windows への Node 導入ガイド

このドキュメントは、Windows への Node の導入と利用を開始するための最初の手順を紹介します。


## Node のインストール

1. [Node 公式サイトのダウンロードページ](https://nodejs.org/en/download/) へ移動します。
1. LTS: Long-term Support, 長期サポートが選択されていることを確認して、Windows Installer (.msi) ファイルをダウンロードします。
1. ダウンロードしたインストーラパッケージを使って Node インストールのセットアップを行います。Custom setting の内容は初期の内容のままで進めます。

> 最先端の Node プログラミングを試してみたい方は、LTS ではなく最新バージョンのインストーラパッケージをダウンロードしてインストールしても構いません。ただし場合によっては一部 Nodeschool workshopper の動きが不安定になるなどのケースがあるかもしれません。


## 動作確認

Windows のコマンドプロンプト (cmd.exe)、もしくは Windows PoweShell を起動します。プロンプトで `node -v` とタイプしてコマンドを実行してみましょう。Node のバージョンが表示されます。

```shell
PS C:\Users\sample> node -v
v4.4.5
```

同じくプロンプトで `npm` とタイプしてコマンド実行します。今度は Node パッケージマネージャ npm のコマンド解説が画面に表示されます。

```
PS C:\Users\sample> npm

Usage: npm <command>

where <command> is one of:
    access, add-user, adduser, apihelp, author, bin, bugs, c,
    cache, completion, config, ddp, dedupe, deprecate, dist-tag,
    dist-tags, docs, edit, explore, faq, find, find-dupes, get,
    help, help-search, home, i, info, init, install, issues, la,
    link, list, ll, ln, login, logout, ls, outdated, owner,
    pack, ping, prefix, prune, publish, r, rb, rebuild, remove,
    repo, restart, rm, root, run-script, s, se, search, set,
    show, shrinkwrap, star, stars, start, stop, t, tag, team,
    test, tst, un, uninstall, unlink, unpublish, unstar, up,
    update, upgrade, v, version, view, whoami

npm <cmd> -h     quick help on <cmd>
npm -l           display full usage info
npm faq          commonly asked questions
npm help <term>  search for help on <term>
npm help npm     involved overview

Specify configs in the ini-formatted file:
    C:\Users\sample\.npmrc
or on the command line via: npm <command> --key value
Config info can be viewed via: npm help config

npm@2.15.5 C:\Program Files\nodejs\node_modules\npm
```


## Nodeschool の workshopper をインストール

最後に、Nodeschoolで用意されている Node 学習のための workshopper をインストールしてみましょう。workshopper のインストールは、先ほど実行してみた Node パッケージマネージャの npm を使って行います。

ここでは、Node の基礎を学ぶことができる `learnyounode` という workshopper をインストールしてみましょう。ターミナル上で、次のようなコマンドを実行してください。

```
PS C:\Users\sample> npm install -g learnyounode
```

**今回実行したコマンドのポイント**

* `npm` は、プログラム実行時にサブコマンドをあわせて指定することで利用します。
* `npm install <package_name>` というコマンドで、指定した Node のパッケージをコンピュータへインストールすることができます。
* `-g` というオプションは「グローバルモード」を指定していて、パッケージのグローバルインストールを行います。これによって、そのパッケージに関連しているソースコードや実行プログラムなどが `/usr/local` 以下に保存されることになります。
* グローバルモードによるインストールで `/usr/local` 以下にファイルが保存されることになるため、`sudo` でコマンド実行しています。

実行に成功すれば、ターミナル画面にはインストールされた leanyounode パッケージと、そのパッケージが依存している関連パッケージがあわせてインストールされた旨が表示されます。

```
C:\Users\sample\AppData\Roaming\npm\learnyounode -> C:\Users\sample\AppData\Roaming\npm\node_modules\learnyounode\bin\learnyounode
learnyounode@3.5.3 C:\Users\sample\AppData\Roaming\npm\node_modules\learnyounode
├── duplexer@0.1.1
├── after@0.8.1
├── boganipsum@0.1.0
├── through@2.3.8
├── combined-stream@1.0.5 (delayed-stream@1.0.0)
├── through2-map@2.0.0 (xtend@4.0.1)
├── colors-tmpl@1.0.0 (colors@1.0.3)
├── workshopper-wrappedexec@0.1.2 (xtend@2.1.2)
├── bl@1.1.2 (readable-stream@2.0.6)
├── through2@2.0.1 (xtend@4.0.1, readable-stream@2.0.6)
├── concat-stream@1.5.1 (inherits@2.0.1, typedarray@0.0.6, readable-stream@2.0.6)
├── hyperquest@1.3.0 (duplexer2@0.0.2, through2@0.6.5)
├── workshopper-exercise@2.7.0 (tuple-stream@0.0.2, xtend@4.0.1, split@1.0.0, wcstring@2.1.1, chalk@1.1.3, i18n-core@2.1.1)
├── rimraf@2.5.2 (glob@7.0.3)
└── workshopper-adventure@4.6.2 (split@1.0.0, chalk@1.1.3, mkdirp@0.5.1, i18n-core@2.1.1, string-to-stream@1.1.0, simple-terminal-menu@1.1.3, msee@0.3.2, commandico@2.0.2, latest-version@2.0.0)
```

> 実行する時期により、表示されるパッケージのバージョン、および依存パッケージの内容そのものが異なる場合があります。

workshopper には、学習のための実行プログラムが梱包されています。 `learnyounode` というコマンドを実行してみましょう。

```
PS C:\Users\sample> learnyounode
```

ターミナルには色鮮やかな画面が表示されましたか？

![learnyounode](learnyounode.png)

learnyounode は他言語対応しており、日本語で学習することができます。キーボードの上下キーを使って `CHOOSE LANGUAGE` までカーソルを動かしてリターンキーを押し、`Japanese (日本語)` を選択します。

さあ、Node 学ぶ準備が整いました。さっそく始めましょう！

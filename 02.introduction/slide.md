# Perl入学式 #1

## Introduction

## Perlって何?
<img src="images/larry.jpg" align='right'>

- 1987年, Larry Wall(右写真)が開発したプログラミング言語.
    - Ruby, Python, PHPと並ぶLL言語(Lightweight Language)の1種.
    - C言語やsed(せど), awk(おーく)の影響を受けた動的型付け言語.
    - RubyやPHPに影響を与えた.
    - ｢Perl｣は言語そのもの, ｢perl｣はその処理系を示す.

## Perlの特徴
- [Wikipediaの記事](http://ja.wikipedia.org/wiki/Perl)から重要なものだけ引用...
    - 強力な文字列処理. 正規表現をサポート.
    - 日本語をはじめとして世界中の言語を処理可能.
    - 自由度の高い文法. 簡潔にプログラムを記述できる.
    - 高い後方互換性を持つ.
    - 数多くのオペレーティングシステムで利用可能.
    - プログラムの実行には事前コンパイルは不要.
    - 有志によって開発された豊富なモジュール.

## TMTOWTDI
- Perlのスローガン. ｢ティムトゥーディー｣と読む.
    - "There's more than one way to do it."
    - ｢やり方はひとつじゃない｣.
- Larryは｢プログラミング言語は, いろんな対象をシンプルに記述する為にある程度複雑でなければならない｣と信じている.
    - Perlは, 同じ意味を持つ処理をいろいろな書き方で表すことができる.

## 簡潔にプログラムを記述できる
    my $number = 123;
    my $string = 'perl';
    print $string . $numbrer . "\n";

- 動的型付け言語なので変数に型は存在しない.
    - `my`というのはスコープの違いを示す. これは明示的に指示する必要がある.
- C言語やJavaのような, 型のキャストなどは必要ない.
- よって, このように数値を格納した変数`$number`と, 文字列を格納した変数`$string`を直接文字列として結合(`.`演算子によって)できる.

## 高い後方互換性
- Perlのバージョンアップによって昔のスクリプトが動かなくなる, ということはほとんどない.
- もちろん, Perlもバージョンアップによる細かい機能変更はある.
    - しかし, 基本的な処理については後方互換性が維持されている.

## 様々な環境で使用可能
- Linuxのほとんどのディストリビューションで標準装備となっている.
    - システムを管理するツールがPerlで書かれている為.
- Pythonもほとんどのディストリビューションで標準装備.
    - 但しほとんどがPython2.
- Rubyを標準で装備するディストリビューションはまだ少ない.
    - Macは標準装備, 但し1.8系.

## 豊富なモジュール
- CPANと呼ばれるアーカイブに, 全世界のPerl Mongerがモジュールを投稿している.
    - Perl Monger ... Perl使いのこと. RubyにおけるRubyist, PythonにおけるPythonistaと同義.
- 例: Encode ... 文字列のエンコードを処理するモジュール.
- 例: Net::Twitter ... TwitterのAPIを操作するモジュール.
- 例: DBD::SQLite ... Perlから, SQLiteのデータベースを操作するモジュール.

## 余談: Perl6について
- Perl5とは別に, Perl6も開発されている.
    - 当初はPerl5の後継となるはずだったが, 後に｢Perl5とは別に開発を進める｣と公式に発表された.
    - よって, Perl5の開発は継続される.
    - 現在の最新版は5.16.3, `perl -v`では, Perl5のバージョン16.3と表記される.

## Perlのコミュニティ
- 世界各地にPerl Mongerのコミュニティが存在する.
    - 地域のPerl Mongrerコミュニティは, (地名).pmを名乗ることが多い.
    - 日本でも, 十数個のコミュニティ, 勉強会が開催されている.

## 地域コミュニティ
- pm.orgに登録されている, 公認のコミュニティ.
    - Hokkaido.pm, Kushiro.pm, Sendai.pm, Niigata.pm, Tokyo.pm, Shibuya.pm, Yokohama.pm, Kamakura.pm, Nagoya.pm, Kansai.pm, Kyoto.pm, Fukuoka.pm
- 非公認のコミュニティ
    - Hachioji.pm, Namba.pm
- 勉強会/イベント
    - Hokkaido.pm Casual, Perl Casual, Perl Beginners, Perl入学式

## YAPC::Asia TOKYO
- YAPC ... Yet Another Perl Conference
    - 年に一度行われる, 日本最大規模のPerlの祭典.
- 今年は9月19日〜21日に開催.
    - ｢エンジニアのエンジニアによるエンジニアのためのお祭り｣.

## Perlを使っている会社
- Line, DeNA, Seesaa, はてな, カヤック, mixi, Mobile Factory, FreakOut, GaiaXなどもPerlを活用しており, 優秀なPerl Mongerが数多く所属している.
- Perlを使ったサービスとしては, はてなの｢はてなダイアリー｣やLineの｢ライブドアブログ｣, オモロキの｢ボケて｣などが有名.

## PerlとCGI
- 一時期, ｢PerlでWebサービスを作るならCGI｣という時代がありましたが, 今はそうではありません.
- 最近は, PSGI(Perl Web Server Gateway Interface)という仕様に対応したWAF(Web Application Framework)を使っての開発が増えています.
    - Perlの代表的なWAFとしては, MojoliciousやAmon2などがあります.
- Perl入学式は｢モダンなPerlを教える｣という方針を取っていますので, CGIについては触れません.

## plenv

## plenvとは
- `plenv`とは, @tokuhiromさんが開発した, 国産のPerl管理ツールです.
    - Rubyの`rbenv`から影響を受けて開発されました.
    - 複数のバージョンのperlを導入し, い分けることができます.
    - モジュールを導入する為の`cpanm`というツールも簡単に導入できます.
    - デフォルトのperlを使ってもいいのですが, モジュールの導入でデフォルトのperlを汚したくない為, plenvを利用します.

## plenvの導入(homebrew)
    $ brew update
    $ brew install plenv

- MacでHomebrewを使っている方は, `brew`コマンドでインストールすることができます.

## plenvの導入(git)
    $ git clone git://github.com/tokuhirom/plenv.git ~/.plenv
    $ sudo apt-get install git # gitのインストール(Ubuntu)

- Linux系OSをお使いの方はgitを使って導入します.
    - まず, このコマンドでplenvをダウンロードします.

## plenvの導入
    $ echo 'export PATH="$HOME/.plenv/bin:$PATH"' >> ~/.bash_profile
    $ echo 'eval "$(plenv init -)"' >> ~/.bash_profile

- plenvへのpathを通します.
    - `~/.bash_profile`はお使いのシェルに応じて適宜変更して下さい.
- Ubuntuをお使いの方で, シェルを`bash`から変更していない方は`~/.bash_profile`のままで問題ありません.

## plenvの導入
    $ source ~/.bash_profile
    $ which plenv
    /home/username/.plenv/bin/plenv

- シェルを再起動したり, `~/.bash_profile`を再度読み込むことで`plenv`が有効になります.
- `which`コマンドで`plenv`にパスが通っているか確認してみましょう.

## plenvでのperlの導入
    $ plenv install 5.16.3

- `plenv`を使ってperlを導入します.
    - 今回は, 現時点での最新の安定版である5.16.3をインストールします.
    - インストールにはそれなりの時間がかかりますので, 暫く待ちましょう.

## plenvでのperlの導入
    $ plenv list
      5.16.3
    * system

- 現在導入済みのperlの一覧を表示する`plenv list`コマンドで, `perl-5.16.3`の導入が成功したか確認してみましょう.
- `system`はデフォルトで入っているperlです.
- 先頭に`*`が付いているものが, 現在有効になっているperlです.

## plenvでのperlの導入
    $ plenv global 5.16.3
    $ plenv list
    * 5.16.3
      system

- `plenv global`コマンドで, デフォルトで使うperlを指定します.
- `plenv global 5.16.3`で, インストールした`perl-5.16.3`を指定すると, `plenv list`の出力がこのように変わるはずです.

## plenvでのperlの導入
    $ perl -v
    This is perl 5, version 16, subversion 3 (v5.16.3) ... (以下略)

- 確かに, `perl-5.16.3`が使われていることが確認できます.

## 現在有効なPerlの確認
    $ plenv version
    5.16.3 (set by /home/username/.plenv/version)

- `plenv version`で, 現在有効になっているPerlと, それがどこで設定されているかを確認することができます.

## エディタ
- Perlの準備が出来ました. 早速, 簡単なコードを書いてみましょう.
- ...その前に, エディタについて軽く説明しておきます.
    - エディタは, プログラミングをコードを書くために必要な道具です.
    - Ubuntuの場合, 標準のgeditでも十分書くことはできます.
- EmacsやVimなど, 既に使い慣れているエディタがある方はそちらをお使いください.

## Sublime Text2
- 特にこだわりのない方は, Sublime Text2を試してみることをおすすめします.
- http://www.sublimetext.com/ からダウンロード.
- ダウンロードしたファイルを右クリック -> `ここに展開する`をクリック.
- `Sublime Text2`というフォルダができるので, その中の`sublime text`をクリックして起動します.

## Hello, world!
- プログラミングの第一歩, Hello, world!に挑戦してみましょう.
    - これは, 端末上に`Hello, world!`という文字列を表示するプログラムです.

## Hello, world!
    print "hello, world!\n";

- エディタにこのようなプログラムを書いて, `hello.pl`という名前で保存しましょう.
    - Perlのスクリプトは`.pl`という拡張子で保存することが多いです.
    - Sublime text2では, `File` -> `Save`で保存できます.
- `print`は, 端末に文字を出力する命令です.
    - `\n`は改行を意味します.
- C言語と同じく, 文の最後には`;`を付けましょう.

## スクリプトの実行
    $ perl hello.pl
    hello, world!

- `perl`の引数に, 実行したいスクリプトファイル名を与えると, そのスクリプトを実行してくれます.

## 練習問題
- print命令を複数個使って, あなたのプロフィール(名前, 年齢, 大学etc...)を表示するスクリプトを書いてみよう.
    - スクリプトの名前は`profile.pl`として, 実行してみましょう.

## plenvとcpanm
    $ plenv install-cpanm

- Perlには, CPANというアーカイブから様々なモジュールを利用することができます.
- `plenv`で導入したperlに, モジュールのインストールを行うツールである`cpanm`を用意しましょう.
- ...といっても難しいことは何もなくて, `plenv install-cpanm`というコマンドを打ち込むだけです.

## plenvとcpanm
    $ cpanm Acme::FizzBuzz

- 試しに, `Acme::FizzBuzz`というモジュールを導入してみましょう.
    - このモジュールは, FizzBuzz問題を解いてくれるモジュールです.
- `Acme`というのは, CPANにおいて｢ジョーク｣なモジュールの為に用意された名前空間です.
- ルーニー･テューンズのロードランナーの中に出てくる, コヨーテに怪しい商品を売るAcme社から来ている... らしい.

## モジュールを使う
    use Acme::FizzBuzz;

- `Acme::FizzBuzz`のインストールが終わったら, この一行を書いたファイルを`fizzbuzz.pl`という名前で保存して, 実行してみましょう.
    - 100までのFizzBuzzの結果が画面上に現れるはずです.

## Perlとモジュール
- ...このように(?), CPANのモジュールは貴方が必要とするであろう様々な機能を提供してくれます.
    - CPANモジュールを組み合わせることで, ｢車輪の再発明｣をすることなくプログラミングをすることができます.
    - Perl入学式の中でも, いくつかのモジュールを利用していきます.

## 今後の予定
- 4月から来年2月まで, 偶数月に開催します(4月, 6月, 8月, 10月, 12月, 2月).
    - 全6回構成の予定です.
    - 参加者募集用のZusaarは, 開催日の1ヶ月前には公開できるようにします.
    - 開催日の告知は, それ以前にできるよう心がけます.

## 今後の予定
- #2から#6までの予定は次のようになっています.
    - #2: Perlの基礎(データの入出力, 変数, 四則演算, 条件分岐, 繰り返し)
    - #3: Perlの基礎(配列, ハッシュ, 正規表現)
    - #4: WAF入門 + モジュール
    - #5: Webサービス開発 前編
    - #6: Webサービス開発 後編
- あくまで予定ですので, 変更が入る可能性があります.

## 今後の予定
- 講義と実践(コーディング)を繰り返すスタイルで進めていきますので, 毎回ノートパソコンの持参をお願いします.
- 質問等は解説中でも遠慮せずに行なって頂ければと思います.
- twitterで`#Perl入学式`というハッシュタグを付けて質問をすれば, スタッフ･サポーターが極力迅速に答えます.

## 今後の予定
- #2以降は, 毎回復習用の宿題を出す予定です.
    - #3以降は, 各回の最初に宿題の答え合わせを行う予定です.
    - 時間が不足しそうな場合, 回答を書いたファイルを配布する, という形式になるかもしれません.

## 今後の予定
- Webサービス開発では, PerlのWAF(ウェブアプリケーションフレームワーク)を使って何かしらのプロダクトを開発しつつ, Perlを学んでいく形になります.
- 去年はMojoliciousを使って｢twitterのような簡易掲示板｣を開発しました.
    - 今年がどうなるかは, 現時点では未定です.

## 今後の予定
- Perl入学式を通して, プログラミングの面白さ, Perlの面白さを実感して頂ければ, それに勝る喜びはありません.
- これから1年間, どうぞ宜しくお願い致します.


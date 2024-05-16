# Python実践入門
---

### 第１章　Pythonはどのような言語か
### 1.1　プログラミング言語としての特徴

**✅ シンプルで読みやすい動的型付き言語**
* 動的型付き言語：変数などのデータ型の宣言がいらないプログラム言語（Python)
* 静的型付き言語：変数などのデータ型の宣言が必要なプログラミング言語

（参考）[動的型付け言語と静的型付け言語の違いとは？](https://webpia.jp/dynamic-static/)

**✔ 記述量が少ない**

C言語(静的型付き)
```
int add(int a, int b) {
    return a + b; 
}
```

Python(動的型付き)
```
def add(a, b):
    return a + b
```
**✔ インデントによるブロックの表現**
　Pythonのコードには処理のブロックを決めるための波括弧{}がなく，インデント（字下げ）の深さでブロックを表現する．よって，**誰が書いても似た見た目のコードになる．**
```
def even_or_odd(n):
    if n % 2 ==0:
       print('偶数です') 
    else:
       print('奇数です')
```

**✅ 教育用プログラミング言語ABCの影響**
　教育用プログラミングやプロトタイピングにも焦点が当てられており，初心者でもできるだけ習得，利用がしやすい設計である．

**✔ 後方互換性の重視**
　古いバージョン(Python3.0以降）で動くコードはほとんどの場合新しいバージョンでも動く．

**✅ 豊富な標準ライブラリ**
* 標準ライブラリ：Pythonをインストールするだけで利用できるライブラリ群　
  
  json, csv, zipfile, sqlite3, cofigparser, pickle
  （↔外部ライブラリ）

**✅ 様々な用途での利用**
　webアプリケーション，プログラミング教育，科学技術計算，OSやインフラなどのシステム管理ツール，サイバーセキュリティ...
　特に科学技術計算や学術的な分野での利用実績が他の汎用言語に比べて多い．

### 1.3　Pythonコミュニティの特徴
**✅コミュニティ主体のOSS**
 Pythonは，コミュニティが主体となってい開発しているフリーのOSS(Open Source Software)である．PythonのソースコードはGitHub上のpython/cpythonリポジトリにあり，誰でもソースコードを読めて開発に参加できる．改変や配布も可能．
 * PyCon：Pythonユーザーが集まるカンファレンス

**✅PEPの存在**
　PEPとは，Python拡張提案(Python Enhancement Proposal)を表し，Pythonのコミュニティに対して情報を提案したり，Pythonに新機能やプロセス，環境などを説明するために設計書である．

* PEP 8 - Style Guide for Python Code
　可読性や一貫性を重要視したPython標準のスタイルガイド．
（例）
  * 命名規則
  * インデントはスペース４つ
  * 括弧の前後の空白は不要
  * 演算子の前後のスペース１つ
　
　実際にコードを書くときはFlake8，pycodestyle，BlackなどのPEP8に準拠したチェッカーやコード自動整形ツールが活用できる．

* PEP 20 - The Zen of Python
　Pythonの設計指針となっている格言集．Pythonを起動後import thisと入力することで確認できる．
```
import this
```

<details>
<summary>The Zen of Python 和訳付き  </summary>  

```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
醜いより美しいほうがいい。

Explicit is better than implicit.
暗示するより明示するほうがいい。

Simple is better than complex.
複雑であるよりは平易であるほうがいい。

Complex is better than complicated.
それでも、込み入っているよりは複雑であるほうがまし。

Flat is better than nested.
ネストは浅いほうがいい。

Sparse is better than dense.
密集しているよりは隙間があるほうがいい。

Readability counts.
読みやすいことは善である。

Special cases aren't special enough to break the rules.
特殊であることはルールを破る理由にならない。

Although practicality beats purity.
しかし、実用性を求めると純粋さが失われることがある。

Errors should never pass silently.
エラーは隠すな、無視するな。

Unless explicitly silenced.
ただし、わざと隠されているのなら見逃せ。

In the face of ambiguity, refuse the temptation to guess.
曖昧なものに出逢ったら、その意味を適当に推測してはいけない。

There should be one-- and preferably only one --obvious way to do it.
何かいいやり方があるはずだ。誰が見ても明らかな、たったひとつのやり方が。

Although that way may not be obvious at first unless you're Dutch.
そのやり方は一目見ただけではわかりにくいかもしれない。オランダ人にだけわかりやすいなんてこともあるかもしれない。

Now is better than never.
ずっとやらないでいるよりは、今やれ。

Although never is often better than *right* now.
でも、今"すぐ"にやるよりはやらないほうがマシなことが多い。

If the implementation is hard to explain, it's a bad idea.
コードの内容を説明するのが難しいのなら、それは悪い実装である。

If the implementation is easy to explain, it may be a good idea.
コードの内容を容易に説明できるのなら、おそらくそれはよい実装である。

Namespaces are one honking great idea -- let's do more of those!
名前空間は優れたアイデアであるため、積極的に利用すべきである。

``` 
</details>  
<br />

* PEP 257 - Docstring Conventions
  ドキュメント(Docstring)の書き方．クラス，メソッド，モジュールなどを対象にしてドキュメントを記述できる．
  * Docstringとは
　コード内で文字を記載する方法の一つ．
　(#)を入れることでそれ以降の文字はコメント，
　(""")または(''')で囲むことでDocstringとなる．

```
def increment(n)
    """引数に1を加えて返す関数

    :param n: 数値
    :return: nに1を足した数値
    """
    return n + 1
```
  ↑　簡潔に説明した1行，空行を1行だけ入れてから詳細を書く，引数ごとに説明を書く，など

参考
[PEP8](https://pep8-ja.readthedocs.io/ja/latest/)
[PEP257](https://peps.python.org/pep-0257/)

---
###　第２章　Pythonのインストールと開発者向けの便利な機能

###　2.1　pythonのインストール

**✅Dockerの利用**
 Dockerとは，コンテナ仮想化と呼ばれる技術を扱うためのマルチプラットフォームなツールで，仮想化されたLinux環境を簡単に配布，実行できる．

### 2.2　Pythonの実行
**✅Pythonインタプリタの2つのモード**
* 対話モード
　ユーザーがその場で入力するコードが対話的に実行される方法．
* スクリプトファイルの実行
  pythonのスクリプトファイルを引数に渡して実行する方法．
  
**✅対話モードの基本的な使い方**
　対話モードは，入力された行を即座に実行（評価）して結果を返す．値に名前をつけた変数を扱うこともでき，変数名だけ入力するとその変数の値が表示される．入録された変数が定義されていない場合はエラーが表示される．

```
>>> 1 + 2
3
>>> print('Hello World') 　# print()の実行
Hello World
>>> a = 1 　# 変数を定義
>>> a  　# 変数の値を確認
1
>>> b = 2
>>> a + b 
3
>>> c  # 定義されていない場合はNameError
NameError: name 'c' is not defined
```
また，モジュールや標準ライブラリを利用できる．
```
>>> import os  # osモジュールをインポート
>>> os.getcwd()  # getcwd()関数でカレントディレクトリの絶対パスを返す
'C:\\Users\\DAISUKE'  
```
<details>
<summary>モジュール，パッケージ，ライブラリ</summary>
  モジュールとは.pyで作られるファイルのこと。ある程度長いプログラムを書く際に.pyファイルに内容を保存。そして使いたい時がきたら、他のPythonファイルからimportでモジュールとして呼び出す。もちろん、呼び出したモジュールに保存されているクラスや関数は呼び出し先でも利用可能.
<br />
  パッケージとはいくつかのモジュールをディレクトリに整理し、ひとまとめにしたもの。機能が似通っているモジュール同士が複数あると、それらをまとめた方が扱いやすくなる。importでパッケージを呼び出すと、パッケージ内にある全てのモジュールの内容を利用できるようになる。
<br />
  ライブラリとはいくつかのパッケージをインストールできる形にまとめたもの。ライブラリには、Pythonに付属していてすぐに使える 標準ライブラリ と、ダウンロードなど追加インストールをしてから利用する 外部ライブラリ がある。機械学習で用いられる「TensorFlow(テンソルフロー)」、グラフ描画に使われるMatplotlib（マットプロットリブ）、データ解析を支援する機能を提供するPandas（パンダス）などは全て外部ライブラリ。
</details>
<br />

**✅対話モードでよく使う組み込み関数**
* 組み込み関数：いつでも利用できる関数．公式ドキュメントの「組み込み関数」に一覧が記載されている．
  
**✔ type()**
　引数で渡したオブジェクト(変数に格納したり，引数や戻り値として利用できるデータ)の型を返してくれる関数．
```
>>> type(1)  # type()は引数に渡した値の型を返す
<class 'int'>
>>> type(1 + 1.0)  # intとfloatの足し算の結果はfloat
<class 'float'>

# print()の戻り値を変数に格納
>>> return_value = print('Hello world')
Hello world

# print()の戻り値の型はNoneType
>>> type(return_value)
<class 'NoneType'>  # type()の実行結果
```

**✔ dir()**
　引数で渡したオブジェクトの属性の一覧をリストで返してくれる組み込み関数．
```
>>> s = 'Hello world'

# 文字列が持つ属性の一覧
# 前後に__がついているものはPythonが暗黙的に利用する属性
>>> dir(s)
['__add__', '__class__', '__contains__', ... 'upper', 'zfill']

# オブジェクトの属性はドット(.)でつなげると参照できる
>>> s.upper 
<built in method upper of str object at 0x100587eb0>
>>> s.upper()  # メソッドは()をつけると実行できる
'HELLO WORLD'
```

**✔ help()**
　引数に渡したオブジェクトのヘルプページを表示してくれてる組み込み関数．
　例）jsonモジュール
```
>>> import json
>>> help(json)
```
**✔ Docstringを使ったヘルプページの作成**
　自分で書いたコードでもDocstringを用意すると，ヘルプページで表示できる．
　例えば，
```
help(increment)
```

**✅スクリプトの実行**
* スクリプト：ソースコードをファイルに書き出し，繰り返し実行可能にしたもの
  例）「こんにちは」を表示するプログラムhello.pyの作成
  Pythonのコードを記述したファイルには，拡張子に.pyを使う．
```
# 関数を定義
def func(message):
    print(message)

# 定義した関数の呼び出し
func('こんにちは')
  ```

```
$ python3 hello.py
```

**✔ モジュールをスクリプトとして実行**


###　第３章　制御フロー

###　3.1　基本となる文法

**✅ インデントによるブロックの表現**
```
>>> import sys
>>> def py2_or_py3():
...     # インデントが下がっている
...     # 実行中のpythonのバージョンを取得
...     major = sys.version_info.major
...     if major < 3:
...         # さらにインデントが下がっている
...         return 'Python 2'
...     else:
...         # 同じくインデントが下がっている
...         return 'Python 3'
...

# 実行環境はPython 3.8
>>> py2_or_py3()
'Python 3'
```

**✔ インデントの幅**
 インデントの幅はスペース4つがおすすめ（PEP8）
 効率を重視してスペース２つに減らすこともある．

**pass文**
　何もしないことを宣言する．
　Pythonでは，ブロックが必要となる箇所が空白であるとエラーが発生する．このとき，pass文を使うと実行中には何もしないが，ブロックが存在することをPythonに伝えることができる．
```
# ２行目はEnterだけを入力
>>> class PracticeBookError(Exception):
...
  File "<stdin>", line 2

   ^
IndentationError: expected an indented block
```
```
>>> class PracticeBookError(Exception)
... pass
...
```
　クラス定義や関数定義では，pass文の代わりにDocstringを使うこともできる．
```
>>> class PracticeBookError(Exception)
...  """モジュール独自の例外の基底クラス"""
```
　
**✔ 変数の利用**
　変数とは，値に名前を付けて再利用可能にしたもの．
　新しい変数を定義したいときは，代入文を書くだけで定義され，すぐに利用できる．
```
# 新しい変数を定義
>>> num = 3
>>> num
3
```
複数の変数をカンマ(,)区切りで並べると，複数の値を一度に代入できる．
```
# 複数の変数を一度に定義
>>> x, y, z = 1, 2, 3
>>> x
1
>>> y
2
>>> z
3
```

　Pythonでは，値が変わらない定数は定義できない（ユーザーが定義する変数はすべて上書きが可能）．PEP8では，変数として利用したい値の名前にはlocal_numberのように小文字，定数として利用したい名前にはCONST_NUMBERのように大文字を使うことが推奨されている．


**✔ 型の宣言がいらない理由**
　Pythonは動的型付き言語であるため，型の宣言が不要である．動的型付き言語は，プログラムの実行中に型を自動で判定しながら処理を行い，暗黙的な型変換は行われない為，コードを書くときは肩を意識する必要がある．

例）数値型と文字列型の値を+演算子でつなぐとエラーがおこる．
```
>>> i = 1
>>> s = '2'
>>> i + s
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```
型をそろえると演算が行われる．
```
# どちらも数値型として演算
>>> i + int(s)
3

# どちらも文字列型として演算
>>> str(i) + s
'12'
```

**✅コメント**
　コメントは，コードの背景や緯度などコードだけでは伝えられない情報を読み手に伝えるために重要な機能である．Ppythonではシャープ(#)以降がコメントとなる．
　#は行頭，行の途中どちらでも書くことができ，複数行にわたるコメントはすべてのコメント行に#をつける．
```
>>> # この行はコメント
... 
>>> def comment(): # ここはコメント
...  pass
...
... # 複数行の
... # コメント
```

###　3.2　条件分岐

**✅ if文**
　条件を指定した処理の分岐．
```
if 条件式1:
    条件式1が真の場合に実行される処理
elif 条件2:
    条件式が1が偽かつ条件式2が真の場合に実行される処理
else:
    すべての条件式が偽の場合に実行される処理    
```
* if文は上から順に評価されていき，最初に真となった節の処理が実行される．
```
>>> import sys
>>> def py2_or_py3():
...   major = sys.version_info.major
...   if major == 2:
...     return 'python 2'
...   elif major == 3:
...     return 'python 3'
...   else:
...     return 'Neither'
...

# 実行環境がPython3.8のとき
>>> py2_or_py3()
'Python3'
```

**✔ 真となる値，偽となる値**
　if文の条件式には，どのような式やオブジェクトも入れられ，真または偽と評価できる．
　Pythonの真理値（真偽値）の判定において，偽となるオブジェクトは次の通り，
* None
* False
* 数値型のゼロ．0や0.0，0j
* 文字列，リスト，辞書，集合などのコンテナオブジェクトの空オブジェクト
* メソッド__bool__()がFalseを返すオブジェクト
* メソッド__bool__()を定義しておらず，メソッド__len__()が0を返すオブジェクト
  
**✔ シンプルな条件式**
例）変数itemがコンテナオブジェクトで，その値が空かどうかをitem内の要素数を使って判定する．
```
>>> def first_item(items):
...   if len(items) > 0:  # 要素数から空かどうかを判定
...     return items[0]  # items内の最初のitemを返す
...   else:
...     return None
...
>>> first_item(['book'])
'book'
>>> first_item([])  # Noneの場合は何も表示されない
>>>
```
空のコンテナオブジェクトが偽になる性質を利用して以下のようにも書ける．
```
>>> def first_item(items):
...   if items:  # 空のコンテナオブジェクトは偽になる
...     return items[0]  # items内の最初のitemを返す
...   else:
...     return None
...
>>> first_item(['book'])
'book'
>>> first_item([])  # Noneの場合は何も表示されない
>>>
```

**✔ if文でよく使う数値の比較**
```
>>> 1 == 1  # 等価の場合にTrue
True
>>> 1 =! 1  # 等価でない場合にTrue
False
>>> 1 > 0  # 左辺が大きい場合にTrue
True
>>> 1 < 0  # 右辺が大きい場合にTrue
False
>>> 1 >= 0  # 左辺が大きいまたは等価の場合にTrue
True
>>> 1 <= 0  # 右辺の時が大きいまたは等価の場合にTrue
```

```
>>> x, y, z = 1, 2, 3

# x < y and y < zと等価
>>> x < y < z
True

# x < y and y > zと等価
>>> x < y > z  # 文法上は正しいが可読性は低い
False
```

**✔ if文でよく使うオブジェクトの比較**
```
>>> x = 'book'
>>> y = 'note'
>>> x == y  # 等価の場合にTrue
False
>>> x != y  # 等価でない場合にTrue
True
>>> x is None  # 同じオブジェクトの場合にTrue
False
>>> x is not None  # 同じオブジェクトでない場合にTrue
True
```
[オブジェクトが同一かどうかの比較する(== 演算子と is 演算子の違い)](https://www.javadrive.jp/python/if/index5.html#:~:text=Python%20%E3%81%A7%E3%81%AF%E6%95%B0%E5%80%A4%E3%82%84%E6%96%87%E5%AD%97%E5%88%97%E3%80%81%E3%83%AA%E3%82%B9%E3%83%88%E3%82%84%E3%82%BF%E3%83%97%E3%83%AB%E3%81%AF%E3%81%99%E3%81%B9%E3%81%A6%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%A7%E3%81%99%E3%80%82%20%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%8C%E5%90%8C%E3%81%98%E3%81%8B%E3%81%A9%E3%81%86%E3%81%8B%E3%82%92%E8%AA%BF%E3%81%B9%E3%82%8B%E3%81%AB%E3%81%AF%20is%20%E6%BC%94%E7%AE%97%E5%AD%90%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%BE%E3%81%99%E3%80%82%20x%20is%20y,not%20is%20y%20x%20%E3%81%A8%20y%20%E3%81%8C%E5%88%A5%E3%81%AE%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%AE%E5%A0%B4%E5%90%88%E3%81%AF%20True)


```
# itemsはリスト
>>> items = ['book']

# itemsに'book'が含まれている場合にTrue
>>> 'book' in items
True

# itemsに'book'が含まれていない場合にTrue
>>> 'book' not in items
False

# countは辞書
>>> count = {'book': 1, 'note': 2}
>>> 'book' in count  # 辞書の場合はキーを用いて判定される
True
>>> 1 in count
False
```

###　3.3　ループ -処理の繰り返し
* for文：リストなどの複数の要素をもつオブジェクトを利用して，要素の数だけブロック内の処理を繰り返す
* while文：条件式が偽になるまでブロック内の処理を繰り返す

**✅for文**
　リストなどの複数の要素をもつオブジェクトを利用して，要素の数だけブロック内の処理を繰り返す
```
for 変数 in イテラブルナオブジェクト:
  繰り返したい処理
```

* イテラブルなオブジェクト：リストなどの複数の要素を持ったオブジェクト
for文では，イテラブルなオブジェクトを持つ要素が1つずつ順番に変数に代入され，要素の数だけ処理が繰り返される．

```
>>> items = [1, 2, 3]
>>> for i in items
... print(f'変数iの値は{i}')  
... # f-stringsの中で、{} の中に変数や式を書くと、その内容が実行時に埋め込まれる
...
変数iの値は1
変数iの値は2
変数iの値は3
...
>>> items
[1, 2, 3]

```

**for文でよく使う組み込み関数**
* range()：ある処理をn回繰り返したいときに利用
```
for 変数 in range(繰り返す回数)
    繰り返したい処理
```
range()に整数nを渡すと，0からn-1までの整数を順に返すイテラブルなオブジェクトを返す
```
>>> for i in range(3)
... print(f'{i}番目の処理')
...
0番目の処理
1番目の処理
2番目の処理
```
<br />

* enumerate()：繰り返し処理の中でリストのインデックスを使いたいときなどに利用

```
for カウント, 変数 in enumerate(イテラブルなオブジェクト)
    繰り返したい処理
```
　enumerate()は，渡されたイテラブルなオブジェクトの各要素と一緒に繰り返しのカウント（0から始まる）を返す．
```
>>> chars = 'word'
>>> for count, char in enumerate(chars):
...   print('{count}番目の文字は{char}')
...
0番目の文字はw
1番目の文字はo
2番目の文字はr
3番目の文字はd
```
**for文のelse節の挙動**
else節には，for文が終了したときに一度だけ実行したい処理を記述する．
break文でループを抜ける際には実行されない．
```
for 変数 in イテラブルなオブジェクト:
    繰り返したい処理
else:
    最後に一度だけ実行したい処理
```
例）else節を利用してリストに奇数が含まれていることをチェック
```
# 奇数がなければメッセージを表示
>>> nums = [2, 4, 6, 8]
>>> for n in nums:
...   if n % 2 == 1:
...     break
... else:
...   print('奇数の値を含めてください')
...
奇数の値を含めてください

# 奇数があれば何も出力しない
>>> nums = [2, 4, 6, 7, 8]
>>> for n in nume:
...   if n % 2 == 1:
...     break
... else:
...   print('奇数の値を含めてください')
...
>>>
```


**for文での変数のスコープ**
変数のスコープ：ある変数が利用できる範囲
Pythonのfor文は，変数のスコープをブロック内に限定しない，つまり，各要素を代入する際に使った変数は通常の変数への代入と同じ扱いになる．

```
# mが未定義であることを確認
>>> m
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'm' is not defined

# for文の変数にmを利用
>>> for m in range(3):
...   pass
...

# mが定義され，最後に代入された値になっている
>>> m
2

# mが定義済みの場合は上書きされる
>>> for m in range(1):
...   pass
...
>>> m
0
```

**✅while文**
条件が真である間はずっと処理を繰り返す．
```
while 条件式:
    繰り返したい処理
```
例）nが3未満である間はprint()関数が実行される．
```
>>> n = 0
>>> while n < 3
...   print(f'変数nの値は{n}')
...   n += 1
...
変数nの値は0
変数nの値は1
変数nの値は2
```

**while文のelseの挙動**
break文でループを抜ける際には実行されない．
```
while 条件式:
    繰り返したい処理
else:
    最後に一度だけ実行したい処理
```

```
>>> n = 0
>>> while n < 3:
...   print(f'変数iの値は{n}')
...   n += 1
... else:
...   print('終了')
...
変数nの値は0
変数nの値は1
変数nの値は2
終了
```

**✅break文**
処理の途中でも現在のループを抜けることができる．else節は実行されない．
例）引数として受け取ったコンテナオブジェクトの中に，文字列'book'を含む要素があるかを調べる．
```
>>> def has_book(items):
...   for item in items:
...     if 'book' in item:
...       print('Found')
...       break  # ループを抜ける
...   else:
...     print('Not Found')
...
>>> has_book(['note'])
Not found
>>> has_book(['note','notebook'])
Found
```
同じ処理をwhile文で書くと，
```
>>> def has_book(items):
...   # pop()はリストの内容を変更するのでコピーを作る
...   copied = items.copy()
...   # 空になるまでループを続ける
...   while copied:
...     # 最後の要素を取り出す
...     item = copied.pop()
...     if 'book' in item:
...       print('Found')
...       break  # ループを抜ける
...    else
...     print('Not found')
...
>>> has_book(['note'])
Not found
>>> has_book(['note', 'notebook'])
Found
```

**continue文**
　ループ内でcontinue文を利用すると，その行以降の処理をスキップして，次のループ処理を開始できる．ループ内にループがあるときは，continue文を利用したループの次の処理を開始する．
例）list_book()関数で，引数として受け取ったコンテナオブジェクトの中の，文字列'book'を含む要素のみを列挙する．
```
>>> def list_books(items):
...   for item in items:
...     if 'book' not in item:
...       # 以降の処理をスキップして次のループに移る．
...       continue
...     print(item)
...
>>> list_book(['note','notebook','sketchbook'])
notebook
sketchbook
```
同様の処理をwhile文で書くと，
```
>>> def lost_book(items):
...   copied = items.copy()
...   while copied:
...     # 先頭の要素を取り出す
...     item = copied.pop(0)
...     if 'book' not in item:
...       # 以降の処理をスキップして次のループに入る
...       continue
...     print(item)
...
>>> list_book(['note','notebook','sketchbook'])
notebook
sketchbook
```
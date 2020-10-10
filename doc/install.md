# Calc Pythonマクロ編集ツールAPSOを導入する

　拡張機能をインストールする。

<!-- more -->

# 成果物

* [github](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212)

# 手順

## 1. ダウンロードする

1. メニュー→`ツール`→`拡張マネージャ`
1. `ほかの機能をオンラインで取得`リンクをクリックする
1. ブラウザが起動する
1. サイトの検索窓に`APSO`を入力して検索する
1. APSOサイトをクリックする
1. サイトから`apso.oxt`ファイルをダウンロードする
1. `apso.oxt`ファイルを任意パスに配置する

![0](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/0.png?raw=true)
![1](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/1.png?raw=true)
![2](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/2.png?raw=true)
![3](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/3.png?raw=true)
![4](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/4.png?raw=true)

## 2. インストールする

1. 拡張マネージャダイアログの`追加`ボタンを押下する
1. `apso.oxt`ファイルを選択する
1. ライセンス条項を最下端までスクロールする
1. `許可`ボタンを押下する
1. リストに`APSO`が追加される

![5](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/5.png?raw=true)
![6](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/6.png?raw=true)
![7](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/7.png?raw=true)
![8](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/8.png?raw=true)

## 3. エディタを設定する

1. 拡張マネージャダイアログのリストから`APSO`を選択する
1. `オプション`ボタンを押下する
1. `エディター`項目に`pluma`や`mousepad`など任意のテキストエディタを入力する

![9](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/9.png?raw=true)

## 4. Pythonコードを書く

1. メニュー→`ツール`→`マクロ`→`Pythonスクリプトの管理`
1. ダイアログのツリーにある`マイマクロ`をクリックする
1. `メニュー`ボタンをクリックする
1. プルダウンから`モジュールの作成`を選ぶ
1. `新規モジュール名`ダイアログにて任意モジュール名を入力する: `user_func`
1. ツリーに作成されたモジュールをクリックする
1. `メニュー`ボタンをクリックする
1. プルダウンから`編集`を選ぶ
1. エディタが起動する
1. 以下のコードを書いて保存する

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# LibreOffice Calc ユーザ定義関数のPython版
def SUM_PY(*args):
    return sum(args)
```

![A](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/A.png?raw=true)
![B](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/B.png?raw=true)
![C](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/C.png?raw=true)
![D](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/D.png?raw=true)
![E](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/E.png?raw=true)

## 5. 使ってみる（失敗）

1. 任意セルに`=SUM_PY(3,3,3)`を入力する
2. `#NAME?`と表示されてしまう

　失敗。期待値は`9`だった。Pythonスクリプトで書いた関数は参照できないのか？

## 6. Pythonシェルで使ってみる（成功）

1. メニュー→`ツール`→`マクロ`→`Pythonスクリプトの管理`
1. `メニュー`ボタンをクリックする
1. プルダウンから`Pythonシェル`を選ぶ
1. `SUM_PY(3,3,3)`コードを入力する
1. `Enter`キーを押下する
1. `9`が表示される

```python
APSO python console [LibreOffice]
3.7.3 (default, Jul 25 2020, 13:03:44) 
[GCC 8.3.0]
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```
```python
>>> SUM_PY(3,3,3)
```
```python
9
```

　成功した。

![F](https://github.com/ytyaru/LibreOffice.Calc.Extension.APSO.20201010155212/blob/master/doc/F.png?raw=true)

# 7. Pythonでユーザ定義関数を作れる？

* [マクロで代用する](https://www.it-swarm-ja.tech/ja/python/libreoffice-calc%E3%82%BB%E3%83%AB%E3%81%A7%E6%95%B0%E5%BC%8F%E3%81%A8%E3%81%97%E3%81%A6python%E9%96%A2%E6%95%B0%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B/944428044/)
* [拡張機能で実現する](https://stackoverflow.com/questions/50785510/define-a-libreoffice-calc-custom-function-in-python)

　どうもBASICと同様の方法で簡単に作ることはできなさそう。

　拡張機能でなら頑張ればできるのかもしれない。大変そうなのでやらない。

# 所感

　ユーザ定義関数はBASICでしか書けない。Pythonで書きたかったのに……。

# 対象環境

* <time datetime="2020-10-10T14:47:16+0900" title="実施日">2020-10-10</time>
* [Raspbierry pi](https://ja.wikipedia.org/wiki/Raspberry_Pi) 4 Model B
* [Raspberry Pi OS](https://ja.wikipedia.org/wiki/Raspbian) buster 10.0 2020-08-20 [※](http://ytyaru.hatenablog.com/entry/2020/10/06/111111)
* [bash](https://ja.wikipedia.org/wiki/Bash) 5.0.3(1)-release
* LibreOffice 6.1.5.2 [※](http://ytyaru.hatenablog.com/entry/2022/07/16/000000) [※](http://ytyaru.hatenablog.com/entry/2022/08/09/000000) [Help](http://ytyaru.hatenablog.com/entry/2022/08/16/000000)

```sh
$ uname -a
Linux raspberrypi 5.4.51-v7l+ #1333 SMP Mon Aug 10 16:51:40 BST 2020 armv7l GNU/Linux
```


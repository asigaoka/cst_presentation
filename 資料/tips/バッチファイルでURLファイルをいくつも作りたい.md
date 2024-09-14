# URLファイルをいくつか作りたいときのtips

# 経緯
* 熊谷さんがこの資料フォルダでホームページを保管しているのを見た。
* 私もやってみようとしたら、htmlファイルでの保存になった。
* htmlファイルだと、周辺の（？って言い方があってるかわからない）ファイルがフォルダになってローカルで見られるように保存される…
* これじゃないかん満載。
* 
* 
* 
* 
* 
* 

## Batchファイルで複数ファイルを作ろう…からの応用が利くのでは！？

- echoコマンドでファイルを作成可能
- エクセルやスプシなどでコマンド入力のたたき台を作る
- パッチファイルに拡張子を変更する
- ファイルやフォルダを一括で作れる
- 応用して、URLファイルを複数作ることができる
- 
- 
- 
- 

# 検証
## 2024.09.09コパイロットとの会話
# 下準備windows　ファイル　linuxの呼び方
WindowsとLinuxではファイルの呼び方や扱い方が異なります。以下にいくつかのポイントをまとめました：

1. **ファイルシステム**:
   - **Windows**: 主にNTFS、FAT32、exFATなどのファイルシステムを使用します。
   - **Linux**: 主にExt4、Ext3、Btrfsなどのファイルシステムを使用します¹。

2. **ファイルパス**:
   - **Windows**: バックスラッシュ（\\）を使用します。例: `C:\Users\Username\Documents`
   - **Linux**: スラッシュ（/）を使用します。例: `/home/username/documents`⁴。

3. **ファイルアクセス**:
   - **WindowsからLinuxファイルにアクセス**: Windows Subsystem for Linux WSL. を使用することで、Windows上でLinuxのファイルシステムにアクセスできます。エクスプローラーのアドレスバーに `\\wsl.localhost` と入力することで、インストールされているLinuxディストリビューションのファイルシステムにアクセスできます⁴。
   - **LinuxからWindowsファイルにアクセス**: Linuxでは、Windowsのドライブが `/mnt` ディレクトリにマウントされます。例えば、Cドライブは `/mnt/c/` です⁴。

これらの方法を使うことで、WindowsとLinux間でファイルをスムーズにやり取りすることができます。何か他に知りたいことがあれば教えてください！¹⁴

ソース: Copilot との会話、 2024/9/9
1. Windows 10でLinuxファイルにアクセスする方法 - MiniTool. https://jp.minitool.com/partition-disk/access-linux-files-from-win10.html.
2. WindowsとWSL2間で相互にファイルの参照やコマンドを実行する .... https://zenn.dev/pino0701/articles/wsl2_windows.
3. インストール不要！WindowsでLinuxコマンドを使う #UNIX - Qiita. https://qiita.com/tetsuy/items/22cba0bc2048967b270a.
4. Windows 10でLinuxファイルにアクセスする方法 - MiniTool. https://bing.com/search?q=windows+%e3%83%95%e3%82%a1%e3%82%a4%e3%83%ab+linux%e3%81%ae%e5%91%bc%e3%81%b3%e6%96%b9.

## windowsはファイル・フォルダと呼んでいるものを、LINUXでは何と呼んでいますか？
Windowsで「ファイル」や「フォルダ」と呼ばれるものは、Linuxでも同じように「ファイル」や「ディレクトリ」と呼ばれます。

- **ファイル**: Windowsと同様に、Linuxでも「ファイル」と呼ばれます。
- **フォルダ**: Linuxでは「ディレクトリ」と呼ばれます。

例えば、Windowsの「C:\Users\Username\Documents」は、Linuxでは「/home/username/documents」となります。

他に何か知りたいことがあれば教えてくださいね！

## バッチファイルを使って.URLファイル（インターネットショートカット）を作成する方法を紹介します。以下の手順に従ってください：

1. **テキストエディタ**（例: メモ帳）を開きます。
2. 以下のコードを入力します：

    ```batch
    @echo off
    echo [InternetShortcut] > "%~dp0example.url"
    echo URL=https://www.example.com >> "%~dp0example.url"
    ```

    このコードは、現在のディレクトリに `example.url` という名前のインターネットショートカットファイルを作成し、そのURLを `https://www.example.com` に設定します⁵⁷。

3. ファイルを `.bat` 拡張子で保存します（例: `create_url.bat`）。
4. 保存したバッチファイルをダブルクリックして実行します。

これで、指定したURLを持つインターネットショートカットファイルが作成されます。他に質問があれば教えてくださいね！⁵⁷

ソース: Copilot との会話、 2024/9/9
1. Windowsバッチファイルでインターネットショートカットを作成し .... https://qiita.com/zono_0/items/c20e25e408f88f1d192d.
2. Create an Internet Shortcut Using Batch File » Winhelponline. https://www.winhelponline.com/blog/create-an-internet-shortcut-using-batch-file/.
3. バッチファイルとスクリプト作成｜Windowsコマンドライン操作を .... https://zenn.dev/teru_whisky/books/10fed5b398fa3a/viewer/9801ac.
4. バッチファイル基礎文法リファレンス #コマンドプロンプト - Qiita. https://qiita.com/kshibamo/items/9368b0b2a4a2f40b61f1.
5. 【bat】URLショートカットをbatで作成する方法 | ふーログ. https://www.fulogabc.net/entry/url-shortcut.
6. Windowsバッチファイル入門：基本から学ぶバッチ処理とcall .... https://yoiegao.net/windows%e3%83%90%e3%83%83%e3%83%81%e3%83%95%e3%82%a1%e3%82%a4%e3%83%ab%e3%81%a7%e6%a5%bd%e3%82%92%e3%81%99%e3%82%8b%ef%bc%9a%e5%9f%ba%e6%9c%ac%e3%81%8b%e3%82%89%e5%ad%a6%e3%81%b6%e3%83%90%e3%83%83/.
7. コマンドプロンプトのバッチファイルで指定のURLからファイル .... https://pslabo.hatenablog.com/entry/2015/12/23/%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%83%97%E3%83%AD%E3%83%B3%E3%83%97%E3%83%88%E3%81%AE%E3%83%90%E3%83%83%E3%83%81%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%A7%E6%8C%87%E5%AE%9A%E3%81%AEURL%E3%81%8B.
8. How to Create and Run a Batch File in Windows 10 and 11 .... https://www.makeuseof.com/tag/write-simple-batch-bat-file/.
9. undefined. https://www.city.hakodate.hokkaido.jp/docs/2022020900014/files/nennreibetsuR0401.csv.
10. en.wikipedia.org. https://en.wikipedia.org/wiki/Batch_file.

## echoは、ファイル作成のコマンドなのですか？もともと存在しないファイル名を入力すると、作成ということでしょうか

`echo` コマンド自体はファイルを作成するためのコマンドではありませんが、リダイレクト（`>` または `>>`）を使用することで、ファイルを作成したり、既存のファイルに内容を追加したりすることができます。

具体的には：

- `>` を使用すると、指定したファイルが存在しない場合は新しく作成され、存在する場合はその内容が上書きされます。
- `>>` を使用すると、指定したファイルが存在しない場合は新しく作成され、存在する場合はその内容に追加されます。

例えば、以下のコマンドは新しいファイル `example.txt` を作成し、その中に「Hello, World!」というテキストを追加します：

```batch
echo Hello, World! > example.txt
```

このようにして、`echo` コマンドとリダイレクトを組み合わせることで、ファイルの作成や内容の追加が可能になります。他に質問があれば教えてくださいね！

## ファイル作成のコマンドではないが、上書をするという行為が、結果的に（同名ファイルが存在しなければ）作成されるということですか？

その通りです！`echo` コマンド自体は単にテキストを出力するためのコマンドですが、リダイレクト（`>` または `>>`）を使うことで、結果的にファイルを作成することができます。

具体的には：

- `>` を使うと、指定したファイルが存在しない場合は新しく作成され、存在する場合はその内容が上書きされます。
- `>>` を使うと、指定したファイルが存在しない場合は新しく作成され、存在する場合はその内容に追加されます。

例えば、以下のコマンドは `example.txt` というファイルが存在しない場合に新しく作成し、その中に「Hello, World!」というテキストを追加します：

```batch
echo Hello, World! > example.txt
```

このようにして、リダイレクトを利用することで、ファイルの作成や内容の追加が可能になります。他に質問があれば教えてくださいね！

## バッチファイルでコマンド操作についてのお役立ち

[Windowsバッチファイル入門>バッチファイルでディレクトリを操作する方法 (mkdir, cd, dir)](https://batchfile.hideharublog.com/batchfile-directory/)
[]()
[]()
[]()
[]()
[]()
[]()
[]()

## URLファイルを作る
(インターネット ショートカット（.url）を作成する方法)[https://windows-waza.com/how-to-create-an-internet-shortcut-url/]
- 小暮は2個目の「ショートカット（.url）をテキストファイルから作成」をしたかったので、結果的にバッチファイルで行けるんじゃない？となった。
[]()
[]()
[]()
[]()
[]()
[]()

## でも、結局こうやってmarkdownMDファイルを作ってリンク貼ったほうが注釈をつけられるので良いかな、とも思ったｗｗｗ

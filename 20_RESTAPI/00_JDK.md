# JDKインストールと設定
- [JDKインストールと設定](#jdkインストールと設定)
  - [インストール前の確認](#インストール前の確認)
  - [JDKダウンロード](#jdkダウンロード)
  - [JDKインストール](#jdkインストール)
  - [環境変数設定](#環境変数設定)
    - [Path 環境変数を設定する](#path-環境変数を設定する)
    - [JAVA_HOME 環境変数を設定する](#java_home-環境変数を設定する)
  - [VSCODEの設定](#vscodeの設定)
    - [java.homeを設定](#javahomeを設定)

---
## インストール前の確認
コマンドプロンプトを起動して次のコマンドを入力する。

```cmd
CMD> javac -version

javac 1.8.0_144
```
バージョンの応答があれば、JDKはインストール済みなので、[VSCODEの設定](#VSCODEの設定)に進みます。

エラーが出た場合はインストールが必要なので、ダウンロード・インストール～設定を実施する。

## JDKダウンロード

[Java SE Development Kit 8 Downloads](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html)にてJava SE Development Kit 8u251のWindows x64	版をダウンロードします。<br/>
ソフトはやはり最新の！という方は、[こちら](https://www.oracle.com/java/technologies/javase-downloads.html) でJava SE 14をダウンロードしていただいても構いません。

ダウンロード済みのインストーラはこちら [&lt; インストーラダウンロード &gt;](https://dilsrv.sharepoint.com/:u:/s/2376/Efu5TujQGg1PjgaN4NUiRHwBvMar6WFMzWOpBsbDDJGiKg?e=F5hrR1)

## JDKインストール
ダウンロードしたファイルを任意の場所で実行すると、インストールが開始される。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_01.jpg)

最初にセットアップ画面が表示されるので[次]ボタンをクリックする。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_02.jpg)

インストールオプションを設定する。特に変更する必要もないので[次]ボタンをクリックする。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_03.jpg)

コピー先インストール先のフォルダを確認される。特に変更する必要もないが、変更する場合は「変更(C)」ボタンから変更して、 [次]ボタンをクリックする。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_04.jpg)

インストールが実行される。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_05.jpg)

この画面が出るとインストールが完了です。

## 環境変数設定
### Path 環境変数を設定する
[スタートメニュー]→[Windowsシステムツール]→[コントロールパネル]→[システム]→[システムの詳細設定]

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_06.jpg)

「詳細設定」のタブを押し、最下部にある「環境変数」のボタンをクリックする。設定されている環境変数の一覧が表示される。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_07.jpg)

まずシステム環境変数「Path」の設定を行う。システム環境変数のリストにある「Path」の行をクリックしてから下の「編集」ボタンをクリックする。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_08.jpg)

環境変数「Path」に設定されている項目が多数出てくるので、ここに新たに1項目を追加する。右上の「新規」ボタンをクリックして**JDKをインストールしたパスに**「bin」フォルダまでを加えたパスを入力する。

例えば、次のような入力になる。
```
C:\Program Files\Java\jdk1.8.0_144\bin
```

注意：導入した時期、JDKのバージョンアップによって 1.8.0の後の3桁の数字は変わるので、設定前に念の為確認しておくこと

### JAVA_HOME 環境変数を設定する
続いて環境変数「JAVA_HOME」の設定を行う。システム環境変数の欄にJAVA_HOMEがない場合は「新規」ボタンをクリックする。既にある場合は、値が正しいかどうかの確認だけで良い。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_09.jpg)

変数名は大文字で「JAVA_HOME」、変数値にはJDKをインストールしたフォルダパスを入力して「OK」をクリックする。こちらはPathの設定と違い、末尾の「￥bin」は不要となる。

これでJDKの準備は整ったが、念のため正しく登録されたかどうかを確認しておく。

コマンドプロンプトを開き、先ほど紹介した方法で確認を行う。

```cmd
CMD> java -version
```

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_10.jpg)

このようにJavaのバージョンが表示されていればインストールは完了です。


## VSCODEの設定

### java.homeを設定

VSCODEサイドメニューの一番下にある歯車アイコンから設定を開く。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_11.png)

設定画面上部の検索窓に　**java.home** と入力すると設定項目が表示されるので、 **setting.jsonで編集** をクリックする。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_12.png)

setting.json 設定編集画面が表示されるので、**java.home** の設定を追加する。

![](https://hiszuk.github.io/prepare/20_RESTAPI/images/jdk_13.png)

例えば、次のような内容を既存ファイルに追記する。
```json
    "java.home": "C:\\Program Files\\Java\\jdk1.8.0_144"
```


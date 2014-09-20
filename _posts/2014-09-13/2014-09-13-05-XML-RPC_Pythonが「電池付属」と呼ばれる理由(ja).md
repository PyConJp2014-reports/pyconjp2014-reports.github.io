---
title: XML-RPC Pythonが「電池付属」と呼ばれる理由(ja)
layout: post
tagline: by Ransui Iso
implementation: "2014-09-13"
time: 14:40 ~ 15:10
---

{% include JB/setup %}

<iframe src="//www.slideshare.net/slideshow/embed_code/39098941" width="427" height="356" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe>

###### **Pythonは電池付属**

Pythonには多くの有用な標準ライブラリが含まれるのでこう呼ばれる  
その中の1つのXML-RPCライブラリの基本的な使い方から応用までを学ぶ  

###### **RPCとは**

* 古い技術である
* でもPythonを使う上で便利なものであるので知ってほしい
* Remote Procedure Call
* Sun RPCが初期のRPC
    * NFSを実装する為に開発されたものであり、NISにも使われている
    * XDRという形式を使ってメッセージをやりとりする
    * Pythonの標準ライブラリにはXDRのシリアライズ/デシリアライズの機能がある

* OSFというグループを作ってUNIXでSun RPCに対抗して作ったものもある
* DCOMも一種のRPCである
* RPCは現在でも色々な所で使われている

###### **RPC, Web-API 何が違うの？**

RPCは言語の拡張機能を提供するという側面が強い  
普通にメソッドを呼び出すようなコードを書くだけで使える  

低いレイヤでRPCを見ると  
リクエスト/レスポンスのやりとりなので  
根本的に違いはない  

IDL(Interface Description Language)によってRPCは記述される  

###### **XML-RPCとは？**

* 交換されるメッセージの形式がXMLになっている
* Sun-RPCのXDRはバイナリ形式である
* 通信はHTTPなので仕組みはRESTと同じ
* 仕様がとてもシンプル(A4で印刷しても4~5ページ)
* Pythonの標準ライブラリにXML-RPCの機能がある
* サーバもクライアントもこれで書ける
* Python2/3でどちらでも使える
* よくあるのはC機能のラッパーである事だが
    * XML-RPCはPythonで実装完結しているので改造も簡単
    * リクエスト/レスポンスの書き方参考としてPythonで読める

###### **サーバ側**

* サーバ側を書いてサーバインスタンスのループを開始しておく
* リクエストが来たら処理してくれるようになる

###### **クライアント側**

* ServerProxyクラスを使うだけ

###### **名前解決どうなってるの？**

* Pythonは動的なので後から属性をくっつける事ができる
    * この性質を利用して、クライアントでコールされたメソッドは  
      名前解決する前に文字列で渡される  

###### **デメリット**

* サーバ側でどういったメソッドが後悔されているのかわからないので見通しが悪い
    * サーバとクライアントで機能の対応付けを守る書き方？

###### **応用**

* RPCはシングルスレッドで動いている
    * ソケットサーバのレベルでスレッド化してしまえば並列処理が可能になる

* pickleでオブジェクトをシリアライズしてあげれば
    * XML-RPCでオブジェクトが渡せるようになる

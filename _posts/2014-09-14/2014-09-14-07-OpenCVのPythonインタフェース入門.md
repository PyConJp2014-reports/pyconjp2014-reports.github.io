---
title: OpenCVのPythonインタフェース入門(ja)
layout: post
tagline: by Masaki Hayashi
implementation: "2014-09-14"
time: 13:00 ~ 13:30
---

{% include JB/setup %}

###### **スライド資料**

[OpenCVのpythonインターフェース入門](http://nbviewer.ipython.org/github/payashim/tutorial-opencv-python-pyconjp2014/blob/master/pyconjp2014_payashim.ipynb)  

###### **OpenCVとは？**

* C++向けのコンピュータビジョン大規模ライブラリ
* コンピュータビジョンに関するモジュールがたくさん入っている
* 全部使いこなすの大変
* OpenCVはC, C++から直接使える
* Python, Javaから使えるラッパーも標準提供されている
* C, C++で関数をコールする感じでPython, Javaでもそのまま使える
* 1系でC向けだったのが2系でC++向けになった

###### **何故Pythonで使うのか？**

* C++と違ってインタラクティブにコンピュータビジョンが実行できるのがよい
* GiMPとかPhotoShopでやるような画像処理をPythonで簡単にできる

###### **Pythonで使ってみる**

* 画像を入力すると画像データがNumpy配列で返ってくる
* 画像を可視化する上ではカラー変換が必要
* matplotlibでも画像を可視化できる？  
matplotlibとは、数値計算結果の可視化を行うPythonのライブラリである  
* ガウシアンブラー  
画像をぼかす手法  
* エッジ検出  
画像の輪郭データだけを取得する  
* 背景差分  
背景として判断されるものだけを抽出する  

###### **質疑応答**

*Question*  

~~~
PythonでOpenCVを使うことのデメリットは？
~~~

*Answer*  

~~~
計算速度が遅い
機械語側に処理を投げるものが多く、C++よりも速度が落ちる  
~~~

*Question*  

~~~
2.4.9と3.0aどちらがいい？
~~~

*Answer*  

~~~
手軽に始めるなら2.4.9が簡単に導入できる
また、GPUによる高速化の機能がC++にはあるが、PythonのOpenCVにはないので注意
~~~


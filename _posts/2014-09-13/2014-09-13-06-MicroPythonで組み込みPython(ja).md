---
title: Micro Pythonで組み込みPython(ja)
layout: post
tagline: by Hirotaka Kawata
implementation: "2014-09-13"
time: 14:00 ~ 14:30
---

{% include JB/setup %}

<iframe src="//www.slideshare.net/slideshow/embed_code/39039083" width="427" height="356" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe>

##### Micro Pythonについて
Micro Pythonとは、
マイコン上で動作する軽量なPythonです  
<br/>

* Python3互換の実装である
* 現状はpyboardというマイコンで動作する
* REPLが使える
* Python内でインラインアセンブリが使える

pyboardは、
[KICKSTARTER](https://www.kickstarter.com/projects/214379695/micro-python-python-for-microcontrollers)
で投資を集めているマイコンボード  

* $20~$24の投資で入手が可能
* 現在は全て発送された段階で入手が不可能

他のマイコンボードについて  

* Raspberry PiはGPIOが少ない(B+では少し増えた)
* ArduinoはC++ライクな言語で開発をする必要がある
* STM32F407評価ボード
    * 秋月電子通商で1750円

Micro Pythonのセットアップ方法

* [Micro Python](https://github.com/micropython/micropython/wiki/Board-STM32F407-Discovery)
* ``$ make BOARD=STM32F4DISC``
* ファームウェアを書き換える必要ある
* USB接続したらREPLが立ち上がる？
* pybモジュールを使う
* pyboardだけに実装されているセンサ等以外の機能は全て使える
* ``pyb.LED`` とか ``pyb.Switch`` とか
* GPIOも使えます
* SC1602 -> LCDディスプレイ(秋月電子通商)
* GR-SAKURAへ移植？

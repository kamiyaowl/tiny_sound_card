# tiny_sound_card
名刺サイズのボードでArduino Pro Mini同等のボードで、mp3を再生したりできるモジュール
ドア開閉時の音声再生モジュールや簡易mp3プレイヤーを簡単に制作できます。

![3d image](https://user-images.githubusercontent.com/4300987/44944524-842db600-ae13-11e8-8a1e-cda6e6e73d0d.png)

## 特徴

* Arduino Pro Miniと同じ開発環境で開発を行え、mp3の音声再生が簡単に行なえます
* スイッチ、mp3再生モジュール、外部スイッチ、SPI、I2Cの準備がしており拡張が容易です
* 表面実装部品が2個のみと、はんだづけの難易度が低いです

## HW仕様

ピン番号 | ボード機能 | ピン機能 | 備考
--------|-------|------|---
D0 | PinHeader | UART RXD | Arduino Bootloader書き込み用
D1 | PinHeader | UART TXD | Arduino Bootloader書き込み用
D2 | LED | Digital Output |
D3 | PinHeader | Digital Input | スイッチ入力用。チャタリング防止回路有
D4 | SW0 | Digital Input | スライドスイッチ
D5 | BTN0 | Digital Input | タクトスイッチ0
D6 | BTN1 | Digital Input | タクトスイッチ1
D7 | BTN2 | Digital Input | タクトスイッチ2
D8 | BTN3 | Digital Input | タクトスイッチ3
D9 | mp3player Control | UART TXD | mp3モジュール制御用
D10 | PinHeader | Digital Output | 外部モジュール接続用SPI
D11 | PinHeader | SPI MOSI | 外部モジュール接続用SPI
D12 | PinHeader | SPI MISO | 外部モジュール接続用SPI
D13 | PinHeader | SPI SCK | 外部モジュール接続用SPI
A0(D14) | mp3player Control | UART RXD | mp3モジュール制御用
A1(D15) | mp3player Control | Digital Input | mp3player再生中にLow
A2(D16) | mp3player Power Control | Digital Output | mp3player電源EN
A3(D17) | mp3player Power Control | Digital Input | mp3player電源/FAULT
A4 | PinHeader | I2C SDA | 外部モジュール接続用I2C
A5 | PinHeader | I2C SCL | 外部モジュール接続用I2C


* スイッチ回路(D3,4,5,6,7,8)にはチャタリング防止回路を実装
* SPI端子はISP(In System Programming)回路も兼用しています
* mp3 playerとはSoftwareSerialを使用して通信を行います
  * [Datasheet](http://akizukidenshi.com/download/ds/dfrobot/DFPlayer_Mini_Manual.pdf)
* mp3 playerモジュールの消費電力が大きいため、ハイサイドスイッチで電源断できるようになっています
  * 不要であれば、U1の1-5pinを短絡してください
   * [Datasheet](https://docs-apac.rs-online.com/webdocs/140d/0900766b8140da8f.pdf)


## SW仕様

準備予定

## License

MIT
